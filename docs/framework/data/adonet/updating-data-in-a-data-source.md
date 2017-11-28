---
title: "Bir veri kaynağındaki verileri güncelleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 91e6a5f2b956816b5e001701a7fbe4a40e7866e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="b8c48-102">Bir veri kaynağındaki verileri güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="b8c48-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="b8c48-103">Verileri (örneğin, INSERT, UPDATE veya DELETE) değiştirme SQL deyimlerini satırları döndürmeyin.</span><span class="sxs-lookup"><span data-stu-id="b8c48-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="b8c48-104">Benzer şekilde, birçok saklı yordamlar bir eylem gerçekleştirmek ancak satırları döndürmüyor.</span><span class="sxs-lookup"><span data-stu-id="b8c48-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="b8c48-105">Satır döndürmeyen komutları yürütmek için Oluştur bir **komutu** uygun SQL komutu nesnesiyle ve **bağlantı**, gerekli dahil olmak üzere **parametreleri**.</span><span class="sxs-lookup"><span data-stu-id="b8c48-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="b8c48-106">Komutu yürütmek **ExecuteNonQuery** yöntemi **komutu** nesnesi.</span><span class="sxs-lookup"><span data-stu-id="b8c48-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="b8c48-107">**ExecuteNonQuery** yöntemi deyimi veya yürütüldü saklı yordam tarafından etkilenen satırların sayısını temsil eden bir tamsayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="b8c48-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="b8c48-108">Birden çok deyime yürütülürse, döndürülen değer tüm yürütülen deyimleri tarafından etkilenen kayıtların toplamıdır.</span><span class="sxs-lookup"><span data-stu-id="b8c48-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8c48-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="b8c48-109">Example</span></span>  
 <span data-ttu-id="b8c48-110">Aşağıdaki kod örneğinde bir veritabanı kullanarak bir kayıt eklemek için INSERT deyimi yürütür **ExecuteNonQuery**.</span><span class="sxs-lookup"><span data-stu-id="b8c48-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="b8c48-111">Aşağıdaki kod örneği örnek kodda tarafından oluşturulan saklı yordam yürütür [katalog işlemleri gerçekleştirme](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b8c48-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span></span> <span data-ttu-id="b8c48-112">Hiçbir satır saklı yordamı tarafından döndürülen böylece **ExecuteNonQuery** yöntemi kullanılır, ancak saklı yordamı bir giriş parametresi alır ve bir output parametresi ve dönüş değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b8c48-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="b8c48-113">İçin <xref:System.Data.OleDb.OleDbCommand> nesnesi **ReturnValue** parametre eklenmelidir **parametreleri** koleksiyonu ilk.</span><span class="sxs-lookup"><span data-stu-id="b8c48-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8c48-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b8c48-114">See Also</span></span>  
 [<span data-ttu-id="b8c48-115">Verileri değiştirmek için komutları kullanarak</span><span class="sxs-lookup"><span data-stu-id="b8c48-115">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [<span data-ttu-id="b8c48-116">Veri kaynakları ile DataAdapters güncelleştiriliyor</span><span class="sxs-lookup"><span data-stu-id="b8c48-116">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="b8c48-117">Komutları ve parametreleri</span><span class="sxs-lookup"><span data-stu-id="b8c48-117">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="b8c48-118">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="b8c48-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)