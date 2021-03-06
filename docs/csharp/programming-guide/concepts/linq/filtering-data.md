---
title: Verileri filtreleme (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: df2f9f1bab7767365be65dbb60fb4af324ae3dab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503303"
---
# <a name="filtering-data-c"></a>Verileri filtreleme (C#)
Filtreleme işlemi yalnızca belirli bir koşulu karşılayan öğeleri içeren sonuç kısıtlama ifade eder. Olarak da bilinir, seçim değildir.  
  
 Aşağıdaki çizimde bir karakter dizisi filtreleme sonuçlarını gösterir. Filtreleme işlemi için koşulu karakter 'A' olması gerektiğini belirtir.  
  
 ![Filtreleme işlemi LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 Seçimi gerçekleştirmek standart sorgu işleci yöntemleri aşağıdaki bölümünde listelenir.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem adı|Açıklama|C# sorgu ifade sözdizimi|Daha fazla bilgi|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Değerleri belirtilen bir türe yayınlanması için kendi yeteneği bağlı olarak seçer.|Yok.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|Where|Bir koşul işlevini temel alan değerleri seçer.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Sorgu ifade sözdizimi örneği  
 Aşağıdaki örnekte `where` bir diziden belirli bir uzunluğa sahip Bu dizelerin filtrelemek için yan tümcesi.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.

- <xref:System.Linq>  
- [Standart sorgu işleçlerine genel bakış (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [where yan tümcesi](../../../../csharp/language-reference/keywords/where-clause.md)  
- [Nasıl yapılır: çalışma zamanında koşul filtrelerini dinamik olarak belirtme](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [Nasıl yapılır: bir derlemenin meta verilerini yansıma (LINQ) (C#) ile sorgulama](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
- [Nasıl yapılır: belirli bir öznitelik veya ada (C#) sahip dosyaları sorgulama](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
- [Nasıl yapılır: herhangi bir sözcük veya alana (LINQ) (C#) göre filtre metin verilerini sıralama veya](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
