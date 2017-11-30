---
title: "Yöntem temelli sorgu sözdizimi örnekler: Küme işleci (LINQ-DataSet)"
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
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d2e33ee55023db7a84109cd3c94a4c8b3b49e1c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="70015-102">Yöntem temelli sorgu sözdizimi örnekler: Küme işleci (LINQ-DataSet)</span><span class="sxs-lookup"><span data-stu-id="70015-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="70015-103">Bu konudaki örnekler nasıl kullanılacağını gösteren <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, ve <xref:System.Linq.Enumerable.Union%2A> kümeleri veri satır değeri tabanlı karşılaştırma işlemleri gerçekleştirmek için işleçler.[ Veri içine bir veri kümesi yükleme](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) bkz [karşılaştırma DataRow](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) hakkında daha fazla bilgi için <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="70015-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="70015-104">`FillDataSet` Bu örneklerde kullanılan yöntemi belirtilen [yüklenirken veri içine bir veri kümesi](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="70015-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="70015-105">Bu konudaki örnekler kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarını AdventureWorks örnek veritabanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="70015-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="70015-106">Aşağıdaki örneklerde bu konudaki `using` / `Imports` deyimleri:</span><span class="sxs-lookup"><span data-stu-id="70015-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="70015-107">Daha fazla bilgi için bkz: [nasıl yapılır: bir LINQ to Visual Studio'da DataSet projesi oluşturma](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="70015-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="70015-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="70015-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="70015-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="70015-109">Example</span></span>  
 <span data-ttu-id="70015-110">Bu örnekte <xref:System.Linq.Enumerable.Distinct%2A> yöntemi bir dizisinde yinelenen öğeleri kaldırın.</span><span class="sxs-lookup"><span data-stu-id="70015-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="70015-111">Dışlama</span><span class="sxs-lookup"><span data-stu-id="70015-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="70015-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="70015-112">Example</span></span>  
 <span data-ttu-id="70015-113">Bu örnekte <xref:System.Linq.Enumerable.Except%2A> ilk tabloda yer alan ancak ikinci görünür kişiler döndürülecek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70015-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="70015-114">Kesiştir</span><span class="sxs-lookup"><span data-stu-id="70015-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="70015-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="70015-115">Example</span></span>  
 <span data-ttu-id="70015-116">Bu örnekte <xref:System.Linq.Enumerable.Intersect%2A> her iki tabloda görünür kişiler döndürülecek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70015-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="70015-117">UNION</span><span class="sxs-lookup"><span data-stu-id="70015-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="70015-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="70015-118">Example</span></span>  
 <span data-ttu-id="70015-119">Bu örnekte <xref:System.Linq.Enumerable.Union%2A> benzersiz kişiler iki tablo birinden döndürülecek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70015-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="70015-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70015-120">See Also</span></span>  
 [<span data-ttu-id="70015-121">Bir veri kümesine veri yükleme</span><span class="sxs-lookup"><span data-stu-id="70015-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="70015-122">LINQ-DataSet örnekleri</span><span class="sxs-lookup"><span data-stu-id="70015-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="70015-123">Standart sorgu işleçlerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="70015-123">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)