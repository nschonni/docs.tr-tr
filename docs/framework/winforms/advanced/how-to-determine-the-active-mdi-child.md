---
title: "Nasıl yapılır: Etkin MDI Alt Öğesini Belirleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 473cf67f01db8735eb3b32a7549296f827e66ef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="9549d-102">Nasıl yapılır: Etkin MDI Alt Öğesini Belirleme</span><span class="sxs-lookup"><span data-stu-id="9549d-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="9549d-103">Bazen, şu anda etkin alt formdaki odağa sahip denetimindeki çalışır bir komut sağlamak isteyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="9549d-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="9549d-104">Örneğin, seçili metnin alt formun metin kutusunda panoya kopyalamak istediğinizi varsayalım.</span><span class="sxs-lookup"><span data-stu-id="9549d-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="9549d-105">Seçili metni panoya kullanmaya kopyalar bir yordam oluşturacak <xref:System.Windows.Forms.Control.Click> Standart Düzen menüsünde kopyalama menü öğesinin olay.</span><span class="sxs-lookup"><span data-stu-id="9549d-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="9549d-106">MDI uygulamanın aynı alt formun sayıda örneği olduğundan yordamı kullanmak için hangi form bilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="9549d-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="9549d-107">Doğru biçimde belirtmek için kullanın <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> odaklı veya, en son etkin alt form döndürür özelliği.</span><span class="sxs-lookup"><span data-stu-id="9549d-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="9549d-108">Bir form üzerinde bazı denetimler sahip olduğunuzda, ayrıca hangi denetimi etkinse belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="9549d-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="9549d-109">Gibi <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> özelliği, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> özelliği etkin alt form üzerinde denetimi odağa sahip döndürür.</span><span class="sxs-lookup"><span data-stu-id="9549d-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="9549d-110">Aşağıdaki yordamda bir alt form menüsünde MDI formu veya bir araç çubuğu düğmesi menüsünde adlı bir kopya yordam gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="9549d-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="9549d-111">(Metni panoya kopyalamak için) etkin MDI alt belirlemek için</span><span class="sxs-lookup"><span data-stu-id="9549d-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1.  <span data-ttu-id="9549d-112">Bir yöntem etkin denetim etkin alt biçiminde metni panoya kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="9549d-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9549d-113">Bu örnek bir MDI ana formu olduğunu varsayar (`Form1`) içeren bir veya daha fazla MDI alt pencereleri olan bir <xref:System.Windows.Forms.RichTextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="9549d-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="9549d-114">Daha fazla bilgi için bkz: [MDI üst formları oluşturma](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9549d-114">For more information, see [Creating MDI Parent Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9549d-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9549d-115">See Also</span></span>  
 [<span data-ttu-id="9549d-116">Birden çok belge arabirimi (MDI) uygulamaları</span><span class="sxs-lookup"><span data-stu-id="9549d-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="9549d-117">Nasıl yapılır: MDI üst formları oluşturma</span><span class="sxs-lookup"><span data-stu-id="9549d-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="9549d-118">Nasıl yapılır: MDI alt formları oluşturma</span><span class="sxs-lookup"><span data-stu-id="9549d-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="9549d-119">Nasıl yapılır: etkin MDI alt öğesine veri gönderme</span><span class="sxs-lookup"><span data-stu-id="9549d-119">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="9549d-120">Nasıl yapılır: MDI alt formlarını düzenleme</span><span class="sxs-lookup"><span data-stu-id="9549d-120">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)