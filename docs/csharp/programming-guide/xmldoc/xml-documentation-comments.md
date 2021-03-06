---
title: XML Belgeleri Yorumları (C# Programlama Kılavuzu)
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: ab4f8fae748455f96ca5ea0255658cc76dd14f97
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48046688"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>XML Belgeleri Yorumları (C# Programlama Kılavuzu)
Visual C#'de, kaynak kodda doğrudan açıklamaların başvurduğu kod bloğunun hemen öncesindeki özel açıklama alanlarına (üç eğik çizgiyle gösterilir) XML öğeleri ekleyerek, kodunuz için belge oluşturabilirsiniz, örneğin:  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 Derleme yaptığınızda [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) seçeneği, derleyicinin tüm XML etiketlerini kaynak kodu ve XML belge dosyası oluşturma için arar. Son belgeleri derleyici tarafından üretilen dosyaya dayalı oluşturmak için özel bir araç oluşturabilir veya gibi bir araç kullanın [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 (Bir XML belgesi açıklamasında tanımlamak istediğiniz gibi işlev belirli XML öğelerini işler) XML öğelerine başvurmak için düzeneğini standart kullanabilirsiniz (`<` ve `>`).  Kod başvurusu genel tanımlayıcılara başvurmak için (`cref`) öğeleri kaçış karakterlerini kullanabilirsiniz (örneğin, `cref="List&lt;T&gt;"`) veya küme ayraçları (`cref="List{T}"`).  Özel bir durum olarak, derleyici, genel tanımlayıcılara başvururken belge açıklamasının yazar için daha az sıkıcı olması için, derleyici tireleri açılı ayraçlar olarak ayrıştırır.  
  
> [!NOTE]
>  XML belge açıklamaları meta veri değildir; oluşturulan derlemeye dahil edilmezler ve bu nedenle yansıtma üzerinden erişilemezler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Belge Açıklamaları için Önerilen Etiketler](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [XML Dosyasını İşleme](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Belge Etiketleri için Sınırlayıcılar](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Nasıl yapılır: XML Belgesi Özelliklerini Kullanma](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 Daha fazla bilgi için bkz.:  
  
-   [/ doc (işlem belgeleri açıklamaları)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
