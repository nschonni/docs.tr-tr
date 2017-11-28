---
title: "Bölümlendirici Denetimine Genel Bakış (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Splitter
helpviewer_keywords: Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e4602796a1a7740adb9a352d0a21fb6c2a58959d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="de3df-102">Bölümlendirici Denetimine Genel Bakış (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="de3df-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="de3df-103">Ancak <xref:System.Windows.Forms.SplitContainer> değiştirir ve işlevlerini ekler <xref:System.Windows.Forms.Splitter> önceki sürümlerinde, denetimin <xref:System.Windows.Forms.Splitter> seçerseniz geriye dönük uyumluluk ve gelecekte kullanım için korunur.</span><span class="sxs-lookup"><span data-stu-id="de3df-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="de3df-104">Windows Forms <xref:System.Windows.Forms.Splitter> denetimlerini çalışma zamanında yuvalanmış denetimleri yeniden boyutlandırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="de3df-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="de3df-105"><xref:System.Windows.Forms.Splitter> Denetimi, veri bölmeleri içeren değişen genişlikleri bilgi farklı zamanlarda Windows Explorer gibi sunmak için veri değişken uzunlukta olması denetimleri ile formlarında sık kullanılır.</span><span class="sxs-lookup"><span data-stu-id="de3df-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="de3df-106">Bölümlendirici denetimi ile çalışma</span><span class="sxs-lookup"><span data-stu-id="de3df-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="de3df-107">Bölümlendirici denetimi tarafından yeniden boyutlandırılabilir bir denetimin kilitli sınırda fare işaretçisini kullanıcı işaret ettiğinde, işaretçi denetimi yeniden boyutlandırılabilir belirtmek için görünümünü değiştirir.</span><span class="sxs-lookup"><span data-stu-id="de3df-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="de3df-108">Bölümlendirici denetimi ile kullanıcı hemen önce olmasından yerleştirilmiş denetim genişletebilir.</span><span class="sxs-lookup"><span data-stu-id="de3df-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="de3df-109">Bu nedenle, yerleşik denetim çalışma zamanında yeniden boyutlandırmak kullanıcı etkinleştirmek için bir kapsayıcı kenarına boyutlandırılmasını denetimi yerleştirme ve ardından bu kapsayıcı aynı tarafına Bölümlendirici denetimi yerleştirme.</span><span class="sxs-lookup"><span data-stu-id="de3df-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3df-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="de3df-110">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="de3df-111">Nasıl yapılır: Windows Forms denetimleri yerleştirme</span><span class="sxs-lookup"><span data-stu-id="de3df-111">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="de3df-112">Windows Forms'ta kullanılacak denetimler</span><span class="sxs-lookup"><span data-stu-id="de3df-112">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)