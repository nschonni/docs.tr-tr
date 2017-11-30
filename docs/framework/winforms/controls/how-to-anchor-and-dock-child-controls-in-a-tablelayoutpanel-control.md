---
title: "Nasıl yapılır: TableLayoutPanel Denetiminde Alt Denetimleri Sabitleme ve Yerleştirme"
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
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15a725f7a5a4b61f826756c4c3f0d2a20c8a5011
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="d37fb-102">Nasıl yapılır: TableLayoutPanel Denetiminde Alt Denetimleri Sabitleme ve Yerleştirme</span><span class="sxs-lookup"><span data-stu-id="d37fb-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="d37fb-103"><xref:System.Windows.Forms.TableLayoutPanel> Kontrol destekler <xref:System.Windows.Forms.Control.Anchor%2A> ve <xref:System.Windows.Forms.Control.Dock%2A> alt denetimlerinden özelliklerinde.</span><span class="sxs-lookup"><span data-stu-id="d37fb-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="d37fb-104">TableLayoutPanel hücre alt denetiminde hizalamak için</span><span class="sxs-lookup"><span data-stu-id="d37fb-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="d37fb-105">Oluşturma bir <xref:System.Windows.Forms.TableLayoutPanel> formunuzda denetim.</span><span class="sxs-lookup"><span data-stu-id="d37fb-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2.  <span data-ttu-id="d37fb-106">Değerini <xref:System.Windows.Forms.TableLayoutPanel> denetimin <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> ve <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> özelliklerine **1**.</span><span class="sxs-lookup"><span data-stu-id="d37fb-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3.  <span data-ttu-id="d37fb-107">Oluşturma bir <xref:System.Windows.Forms.Button> denetim <xref:System.Windows.Forms.TableLayoutPanel> denetim.</span><span class="sxs-lookup"><span data-stu-id="d37fb-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="d37fb-108"><xref:System.Windows.Forms.Button> Hücrenin sol üst köşesinde yer kaplar.</span><span class="sxs-lookup"><span data-stu-id="d37fb-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4.  <span data-ttu-id="d37fb-109">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `Left`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="d37fb-110"><xref:System.Windows.Forms.Button> Denetimi taşır hücrenin sol kenarlık ile hizalamak.</span><span class="sxs-lookup"><span data-stu-id="d37fb-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d37fb-111">Bu davranış diğer kapsayıcı denetimleri davranışından farklıdır.</span><span class="sxs-lookup"><span data-stu-id="d37fb-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="d37fb-112">Kapsayıcı denetimleri, ne zaman alt denetim taşımaz <xref:System.Windows.Forms.Control.Anchor%2A> özelliği ayarlanmış ve bağlantılı denetim ile üst kapsayıcının sınır arasındaki uzaklığı zaman sabit <xref:System.Windows.Forms.Control.Anchor%2A> özelliği ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="d37fb-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5.  <span data-ttu-id="d37fb-113">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="d37fb-114"><xref:System.Windows.Forms.Button> Denetim hücrenin sol üst köşesinde kaplar taşır.</span><span class="sxs-lookup"><span data-stu-id="d37fb-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6.  <span data-ttu-id="d37fb-115">Yineleme 5. adımını bir değerle `Top, Right` taşımak için <xref:System.Windows.Forms.Button> hücrenin sağ üst köşesinde denetimine.</span><span class="sxs-lookup"><span data-stu-id="d37fb-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="d37fb-116">Yineleme değerlerle `Bottom, Left` ve `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="d37fb-117">TableLayoutPanel hücre alt denetiminde uzatmak için</span><span class="sxs-lookup"><span data-stu-id="d37fb-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="d37fb-118">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="d37fb-119"><xref:System.Windows.Forms.Button> Denetim yeniden boyutlandırılır hücre boyunca uzatmak için.</span><span class="sxs-lookup"><span data-stu-id="d37fb-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d37fb-120">Bu davranış diğer kapsayıcı denetimleri davranışından farklıdır.</span><span class="sxs-lookup"><span data-stu-id="d37fb-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="d37fb-121">Diğer kapsayıcı denetimleri alt denetim değil ne zaman yeniden boyutlandırılabilir <xref:System.Windows.Forms.Control.Anchor%2A> özelliği ayarlanmış `Left, Right` veya `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2.  <span data-ttu-id="d37fb-122">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="d37fb-123"><xref:System.Windows.Forms.Button> Denetim yeniden boyutlandırılır üstten hücrenin en altına uzatmak için.</span><span class="sxs-lookup"><span data-stu-id="d37fb-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3.  <span data-ttu-id="d37fb-124">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="d37fb-125"><xref:System.Windows.Forms.Button> Denetim yeniden boyutlandırılır hücreyi doldurmak için.</span><span class="sxs-lookup"><span data-stu-id="d37fb-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4.  <span data-ttu-id="d37fb-126">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğine `None`.</span><span class="sxs-lookup"><span data-stu-id="d37fb-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="d37fb-127"><xref:System.Windows.Forms.Button> Denetim yeniden boyutlandırılabilir ve hücrede ortalanır.</span><span class="sxs-lookup"><span data-stu-id="d37fb-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5.  <span data-ttu-id="d37fb-128">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Dock%2A> özelliğine <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="d37fb-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="d37fb-129"><xref:System.Windows.Forms.Button> Denetimi taşır hücrenin sol kenarlık ile hizalamak.</span><span class="sxs-lookup"><span data-stu-id="d37fb-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="d37fb-130"><xref:System.Windows.Forms.Button> Denetim genişliğini korur, ancak kendi yüksekliğini hücreyi dikey doldurmak için yeniden boyutlandırılmış.</span><span class="sxs-lookup"><span data-stu-id="d37fb-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d37fb-131">Kapsayıcı denetimleri oluşan aynı davranış budur.</span><span class="sxs-lookup"><span data-stu-id="d37fb-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6.  <span data-ttu-id="d37fb-132">Değerini değiştirme <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Dock%2A> özelliğine <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="d37fb-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="d37fb-133"><xref:System.Windows.Forms.Button> Denetim yeniden boyutlandırılır hücreyi doldurmak için.</span><span class="sxs-lookup"><span data-stu-id="d37fb-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d37fb-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="d37fb-134">Example</span></span>  
 <span data-ttu-id="d37fb-135">Beş düğmeden beş ayrı bağlantılı aşağıda gösterilmiştir <xref:System.Windows.Forms.TableLayoutPanel> hücreleri.</span><span class="sxs-lookup"><span data-stu-id="d37fb-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d37fb-136">![TableLayoutPanel Bağlama](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="d37fb-136">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="d37fb-137">Aşağıdaki çizimde dört ayrı köşelerinde bağlantılı dört düğme gösterilmektedir <xref:System.Windows.Forms.TableLayoutPanel> hücreleri.</span><span class="sxs-lookup"><span data-stu-id="d37fb-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d37fb-138">![TableLayoutPanel Bağlama](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="d37fb-138">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="d37fb-139">Aşağıdaki çizim üç ayrı sabitleme tarafından uzatılmış üç düğme göstermektedir <xref:System.Windows.Forms.TableLayoutPanel> hücreleri.</span><span class="sxs-lookup"><span data-stu-id="d37fb-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d37fb-140">![TableLayoutPanel Bağlama](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="d37fb-140">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="d37fb-141">Aşağıdaki kod örneğinde tüm bileşimleri gösterilmektedir <xref:System.Windows.Forms.Control.Anchor%2A> özellik değerleri için bir <xref:System.Windows.Forms.Button> denetim bir <xref:System.Windows.Forms.TableLayoutPanel> denetim.</span><span class="sxs-lookup"><span data-stu-id="d37fb-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d37fb-142">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="d37fb-142">Compiling the Code</span></span>  
 <span data-ttu-id="d37fb-143">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="d37fb-143">This example requires:</span></span>  
  
-   <span data-ttu-id="d37fb-144">Sistem, System.Data, System.Drawing ve System.Windows.Forms derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="d37fb-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d37fb-145">Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d37fb-145">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d37fb-146">Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.</span><span class="sxs-lookup"><span data-stu-id="d37fb-146">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="d37fb-147">Ayrıca bkz. [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d37fb-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d37fb-148">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d37fb-148">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="d37fb-149">TableLayoutPanel denetimi</span><span class="sxs-lookup"><span data-stu-id="d37fb-149">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)