---
title: "Kullanarak bir veri kümesi doldurma ya da daha fazla REF imleçler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: 99863e79-5b00-467e-a105-4ffa42de3ff7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1ef5633c53f537f34a3c72ede89f55b1beac09a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="filling-a-dataset-using-one-or-more-ref-cursors"></a><span data-ttu-id="65f4d-102">Kullanarak bir veri kümesi doldurma ya da daha fazla REF imleçler</span><span class="sxs-lookup"><span data-stu-id="65f4d-102">Filling a DataSet Using One or More REF CURSORs</span></span>
<span data-ttu-id="65f4d-103">Bu Microsoft Visual Basic örnek doldurur ve iki REF İMLEÇ parametreleri döndüren bir PL/SQL saklı yordamı yürüten bir <xref:System.Data.DataSet> satırlarla döndürülür.</span><span class="sxs-lookup"><span data-stu-id="65f4d-103">This Microsoft Visual Basic example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
```vb  
Private Sub Button1_Click(ByVal sender As Object, _  
  ByVal e As System.EventArgs) Handles Button1.Click  
  
  Dim connString As New String(_  
    "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Dim ds As New DataSet()  
    Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_TWO_CURSORS"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter( _  
      "EMPCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
    cmd.Parameters.Add(New OracleParameter( _  
      "DEPTCURSOR", OracleType.Cursor)).Direction = _  
       ParameterDirection.Output  
  
    Dim da As New OracleDataAdapter(cmd)  
    da.TableMappings.Add("Table", "Emp")  
    da.TableMappings.Add("Table1", "Dept")  
    da.Fill(ds)  
  
    ds.Relations.Add("EmpDept", ds.Tables("Dept").Columns("Deptno"), _  
      ds.Tables("Emp").Columns("Deptno"), False)  
  
    DataGrid1.DataSource = ds.Tables("Dept")  
  End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="65f4d-104">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="65f4d-104">See Also</span></span>  
 [<span data-ttu-id="65f4d-105">Oracle REF imleçler</span><span class="sxs-lookup"><span data-stu-id="65f4d-105">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 [<span data-ttu-id="65f4d-106">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="65f4d-106">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)