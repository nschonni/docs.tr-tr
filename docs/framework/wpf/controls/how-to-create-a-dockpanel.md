---
title: "Nasıl yapılır: DockPanel Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7fab2d0f7dfe94857a3c6c5cb6e8414360d3078e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="2da98-102">Nasıl yapılır: DockPanel Oluşturma</span><span class="sxs-lookup"><span data-stu-id="2da98-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="2da98-103">Örnek</span><span class="sxs-lookup"><span data-stu-id="2da98-103">Example</span></span>  
 <span data-ttu-id="2da98-104">Aşağıdaki örnek, oluşturur ve bir örneğini kullanan <xref:System.Windows.Controls.DockPanel> kodu kullanarak.</span><span class="sxs-lookup"><span data-stu-id="2da98-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="2da98-105">Örnek alanı beş oluşturarak bölümlemek gösterilmiştir <xref:System.Windows.Shapes.Rectangle> öğeleri ve (yerleştirme) boşluğu üst içinde bunları <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="2da98-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="2da98-106">Varsayılan ayar korursanız, son dikdörtgen tüm kalan ayrılmamış alanı doldurur.</span><span class="sxs-lookup"><span data-stu-id="2da98-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2da98-107">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2da98-107">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.Dock>  
 [<span data-ttu-id="2da98-108">Paneller Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="2da98-108">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)