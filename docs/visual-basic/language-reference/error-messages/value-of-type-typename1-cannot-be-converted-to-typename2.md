---
title: Değer türü &#39; &lt;typename1&gt; &#39; dönüştürülemiyor &#39; &lt;typename2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 9b3c029ed7bf73ff92dba65438d797b27fa135f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595244"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Değer türü &#39; &lt;typename1&gt; &#39; dönüştürülemiyor &#39; &lt;typename2&gt;&#39;
Türündeki değeri '\<typename1 >' şekilde dönüştürülemeyen '\<typename2 >'. Tür uyuşmazlığı proje başvurusu derleme dosyası başvurusuyla karıştırılması nedeniyle olabilir '\<assemblyname >'. Dosya başvurusunu değiştirmeyi deneyin '\<filepath >' projesindeki '\<projectname1 >' proje başvuru '\<projectname2 >'.  
  
 Burada bir proje proje başvurusu ve bir dosya başvuru yapar bir durumda, bir tür için başka bir dönüştürülebileceğinden derleyici garanti edemez.  
  
 Aşağıdaki sözde kod bu hatayı üreten bir durumu gösterir.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Proje `P1` dolaylı proje başvurusu aracılığıyla projeyi yapar `P2` projesine `P3`ve aynı zamanda doğrudan dosya başvurusu `P3`. Bildirimi `commonObject` dosya başvurusu için kullandığı `P3`, while çağrısı `P2.getCommonClass` proje başvurusu kullanan `P3`.  
  
 Bu durumda dosya başvurusunu bir dosya yolu ve çıkış dosyasının adı belirtir bir sorundur `P3` (genellikle p3.dll) kaynak projesini proje başvuruları tanımlayın sırada (`P3`) proje adıyla. Bu nedenle, derleme, tür garanti edemez `P3.commonClass` iki farklı başvurular aracılığıyla aynı kaynak kodu alanından gelir.  
  
 Bu durum genellikle ortaya başvuruları'ne zaman proje ve başvurulara karma. Önceki çizimde, sorun varsa oluşmaz `P1` doğrudan proje başvurusu yapılan `P3` yerine dosya başvurusu.  
  
 **Hata Kimliği:** BC30955  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Proje başvurusu dosya başvurusunu değiştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic'de tür dönüştürmeleri](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project)  
 
