---
title: "Yöntem temelli sorgu sözdizimi örnekleri: filtreleme"
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
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b81e163a6d326135f8031c6ef43af698d9c706b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="b958d-102">Yöntem temelli sorgu sözdizimi örnekleri: filtreleme</span><span class="sxs-lookup"><span data-stu-id="b958d-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="b958d-103">Bu konudaki örnekler nasıl kullanılacağını gösteren `Where` ve `Where…Contains` sorgulamak için yöntemleri [AdventureWorks satış modeli](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) yöntemi tabanlı sorgu sözdizimini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="b958d-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="b958d-104">Not, burada...`Contains`</span><span class="sxs-lookup"><span data-stu-id="b958d-104">Note, Where…`Contains`</span></span> <span data-ttu-id="b958d-105">bir parçası olarak kullanılan bir [sorgu derlenmiş](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="b958d-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="b958d-106">Bu örneklerde kullanılan AdventureWorks satış modeli AdventureWorks örnek veritabanını kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b958d-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b958d-107">Aşağıdaki örneklerde bu konudaki `using` / `Imports` deyimleri:</span><span class="sxs-lookup"><span data-stu-id="b958d-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="b958d-108">Where</span><span class="sxs-lookup"><span data-stu-id="b958d-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="b958d-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-109">Example</span></span>  
 <span data-ttu-id="b958d-110">Aşağıdaki örnek, tüm çevrimiçi siparişleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b958d-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="b958d-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-111">Example</span></span>  
 <span data-ttu-id="b958d-112">Aşağıdaki örnek, sipariş miktarı 2 değerinden 6'dan büyük ve olduğu siparişleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b958d-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="b958d-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-113">Example</span></span>  
 <span data-ttu-id="b958d-114">Aşağıdaki örnekte tüm kırmızı renkli ürünleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b958d-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="b958d-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-115">Example</span></span>  
 <span data-ttu-id="b958d-116">Aşağıdaki örnek kullanır `Where` 1 Aralık 2003'ten sonra yapılan siparişleri ve kullandığı bulmak için yöntem `order.SalesOrderDetail` her sipariş için ayrıntıları almak için gezinme özelliği.</span><span class="sxs-lookup"><span data-stu-id="b958d-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="b958d-117">WHERE... İçerir</span><span class="sxs-lookup"><span data-stu-id="b958d-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="b958d-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-118">Example</span></span>  
 <span data-ttu-id="b958d-119">Aşağıdaki örnek, bir parçası olarak bir dizi kullanır bir `Where…Contains` sahip tüm ürünleri bulmak için yan tümcesi bir `ProductModelID` dizisinde bulunan bir değeri ile eşleşen.</span><span class="sxs-lookup"><span data-stu-id="b958d-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="b958d-120">Koşulda bir parçası olarak bir `Where…Contains` yan tümcesi, kullanabileceğiniz bir <xref:System.Array>, <xref:System.Collections.Generic.List%601>, veya uygulayan herhangi bir türde bir koleksiyonu <xref:System.Collections.Generic.IEnumerable%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="b958d-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b958d-121">Bildirme ve bir koleksiyonu bir LINQ to Entities sorgusunda başlatır.</span><span class="sxs-lookup"><span data-stu-id="b958d-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="b958d-122">Sonraki örnek daha fazla bilgi için bkz.</span><span class="sxs-lookup"><span data-stu-id="b958d-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="b958d-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="b958d-123">Example</span></span>  
 <span data-ttu-id="b958d-124">Aşağıdaki örnek bildirir ve dizilerde başlatır bir `Where…Contains` sahip tüm ürünleri bulmak için yan tümcesi bir `ProductModelID` veya `Size` dizilerde bir değeri ile eşleşen.</span><span class="sxs-lookup"><span data-stu-id="b958d-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b958d-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b958d-125">See Also</span></span>  
 [<span data-ttu-id="b958d-126">LINQ to Entities sorguları</span><span class="sxs-lookup"><span data-stu-id="b958d-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)