---
title: Nesneler koleksiyonunu sorgulama
description: "Koleksiyonları nasıl sorgu."
keywords: .NET, .NET core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 74d6c1f080c3e70867f5d2f074315bd1d8486bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="8b8a3-104">Nesneler koleksiyonunu sorgulama</span><span class="sxs-lookup"><span data-stu-id="8b8a3-104">Query a collection of objects</span></span>
<span data-ttu-id="8b8a3-105">Bu örnek listesini basit bir sorgu gerçekleştirme gösterir `Student` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="8b8a3-106">Her `Student` nesnesi Öğrenci ve dört incelemelerde öğrencinin başarı gösteren liste hakkında bazı temel bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="8b8a3-107">Aynı kullanan çok sayıda diğer örnekler için bu bölümdeki framework olarak bu uygulamaya hizmet `students` veri kaynağı.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8a3-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="8b8a3-108">Example</span></span>  
 <span data-ttu-id="8b8a3-109">Aşağıdaki sorgu 90 veya kendi ilk incelemesi üzerinde daha büyük bir puan alınan Öğrenciler döndürür.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="8b8a3-110">Bu sorgu, deneme etkinleştirmek kasıtlı olarak basit bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="8b8a3-111">Örneğin, daha fazla koşullarında deneyebilirsiniz `where` yan tümcesi ya da kullanım bir `orderby` sonuçları sıralamak için yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="8b8a3-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-112">See also</span></span>  
 [<span data-ttu-id="8b8a3-113">LINQ Sorgu ifadeleri</span><span class="sxs-lookup"><span data-stu-id="8b8a3-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="8b8a3-114">Ara değerli dizeler</span><span class="sxs-lookup"><span data-stu-id="8b8a3-114">Interpolated Strings</span></span>](../language-reference/keywords/interpolated-strings.md)