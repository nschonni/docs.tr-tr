---
title: "Nasıl Yapılır: ToolStripTextBox'nu bir ToolStrip'nin Kalan Genişliğini Kaplayacak Şekilde Genişletme (Windows Forms)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Nasıl Yapılır: ToolStripTextBox'nu bir ToolStrip'nin Kalan Genişliğini Kaplayacak Şekilde Genişletme (Windows Forms)
Ayarladığınızda <xref:System.Windows.Forms.ToolStrip.Stretch%2A> özelliği bir <xref:System.Windows.Forms.ToolStrip> denetimini `true`, denetimin kapsayıcısının uçtan uca doldurur ve öğenin kapsayıcısına göre yeniden boyutlandırır olduğunda yeniden boyutlandırır. Bu yapılandırmada, öğeyi denetiminde gibi uzatmak yararlı bir <xref:System.Windows.Forms.ToolStripTextBox>, kullanılabilir alanı dolduracak şekilde ve denetimi yeniden boyutlandırır yeniden boyutlandırmak için. Görünüm ve davranış Microsoft® Internet Explorer Adres çubuğuna benzer elde etmek istiyorsanız bu uzatma Örneğin, yararlıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde türetilmiş bir sınıf sağlar <xref:System.Windows.Forms.ToolStripTextBox> adlı `ToolStripSpringTextBox`. Bu sınıf geçersiz kılmaları <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> üst kullanılabilir genişliğini hesaplamak için yöntem <xref:System.Windows.Forms.ToolStrip> diğer tüm öğeleri birleşik genişliğini çıkarılmasıyla denetim. Bu kod örneği de sağlayan bir <xref:System.Windows.Forms.Form> sınıfı ve bir `Program` yeni davranışı göstermek için sınıf.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem, System.Drawing ve System.Windows.Forms derlemelerine başvurular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [ToolStrip Denetim, Mimarisi](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Nasıl yapılır: Bir StatusStrip içinde Spring Özelliğini Etkileşimli Kullanma](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
