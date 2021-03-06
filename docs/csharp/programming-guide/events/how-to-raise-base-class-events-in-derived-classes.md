---
title: 'Nasıl yapılır: Türetilmiş Sınıflarda Temel Sınıf Olayları Oluşturma (C# Programlama Kılavuzu)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 51bc6621d49bbb16313c900a92b539c30eb61ff0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525205"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>Nasıl yapılır: Türetilmiş Sınıflarda Temel Sınıf Olayları Oluşturma (C# Programlama Kılavuzu)
Aşağıdaki basit örnekte, böylece türetilmiş sınıflardan de oluşturulabilir, bir temel sınıf olayları bildirmek için standart bir yolunu gösterir. Bu düzen Windows Forms sınıfları yaygın olarak kullanılan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] sınıf kitaplığı.  
  
 Diğer sınıflar için temel sınıf olarak kullanılan bir sınıfı oluşturduğunuzda, olaylar yalnızca gelen bunları bildiren sınıfın içinden çağrılabilen temsilciyi özel bir tür olması, düşünmelisiniz. Türetilmiş sınıflar temel sınıf içinde bildirilen olayları doğrudan çağrılamıyor. Çoğu zaman, yalnızca taban sınıfı tarafından oluşturulan bir olay bazen isteyebilirsiniz ancak türetilen sınıfın temel sınıf olayları çağırmak etkinleştirmeniz gerekir. Bunu yapmak için olay sarmalar ve taban sınıfta korumalı çağrılıyor bir yöntem oluşturabilirsiniz. Türetilen sınıfların çağrı yapma veya bu çağrılıyor yöntemini geçersiz kılma, olay dolaylı olarak çağırabilirsiniz.  
  
> [!NOTE]
>  Sanal bir temel sınıf olayları bildirme değil ve bunları türetilen bir sınıfta geçersiz kılar. C# Derleyici doğru bu işlemez ve türetilmiş bir olaya abone aslında temel sınıf olaya abone olup olmadığını tahmin edilemez.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Olaylar](../../../csharp/programming-guide/events/index.md)  
- [Temsilciler](../../../csharp/programming-guide/delegates/index.md)  
- [Erişim Değiştiricileri](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [Windows Forms'ta Olay İşleyicileri Oluşturma](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
