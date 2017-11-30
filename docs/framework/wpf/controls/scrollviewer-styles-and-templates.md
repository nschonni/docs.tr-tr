---
title: "ScrollViewer Stilleri ve Şablonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac02896708744bc9b1c2d017da4e6f56ac32b53a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="4667d-102">ScrollViewer Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="4667d-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="4667d-103">Stilleri ve şablonları için bu konuda açıklanmaktadır <xref:System.Windows.Controls.ScrollViewer> denetim.</span><span class="sxs-lookup"><span data-stu-id="4667d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="4667d-104">Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetimi benzersiz bir görünüm vermek için.</span><span class="sxs-lookup"><span data-stu-id="4667d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4667d-105">Daha fazla bilgi için bkz: [ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4667d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="4667d-106">ScrollViewer bölümleri</span><span class="sxs-lookup"><span data-stu-id="4667d-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="4667d-107">Adlandırılmış bölümleri için aşağıdaki tabloda listelenmektedir <xref:System.Windows.Controls.ScrollViewer> denetim.</span><span class="sxs-lookup"><span data-stu-id="4667d-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="4667d-108">Bölümü</span><span class="sxs-lookup"><span data-stu-id="4667d-108">Part</span></span>|<span data-ttu-id="4667d-109">Tür</span><span class="sxs-lookup"><span data-stu-id="4667d-109">Type</span></span>|<span data-ttu-id="4667d-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4667d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4667d-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="4667d-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="4667d-112">İçeriği için yer tutucu <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="4667d-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="4667d-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="4667d-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="4667d-114"><xref:System.Windows.Controls.Primitives.ScrollBar> İçeriği yatay kaydırma için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4667d-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="4667d-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="4667d-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="4667d-116"><xref:System.Windows.Controls.Primitives.ScrollBar> İçeriği dikey olarak kaydırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4667d-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="4667d-117">ScrollViewer durumları</span><span class="sxs-lookup"><span data-stu-id="4667d-117">ScrollViewer States</span></span>  
 <span data-ttu-id="4667d-118">Aşağıdaki tablo için görsel durumlarını listeler <xref:System.Windows.Controls.ScrollViewer> denetim.</span><span class="sxs-lookup"><span data-stu-id="4667d-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="4667d-119">VisualState adı</span><span class="sxs-lookup"><span data-stu-id="4667d-119">VisualState Name</span></span>|<span data-ttu-id="4667d-120">VisualStateGroup adı</span><span class="sxs-lookup"><span data-stu-id="4667d-120">VisualStateGroup Name</span></span>|<span data-ttu-id="4667d-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4667d-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4667d-122">Geçerli</span><span class="sxs-lookup"><span data-stu-id="4667d-122">Valid</span></span>|<span data-ttu-id="4667d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4667d-123">ValidationStates</span></span>|<span data-ttu-id="4667d-124">Denetim kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> iliştirilmiş özelliği `false`.</span><span class="sxs-lookup"><span data-stu-id="4667d-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4667d-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4667d-125">InvalidFocused</span></span>|<span data-ttu-id="4667d-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4667d-126">ValidationStates</span></span>|<span data-ttu-id="4667d-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="4667d-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4667d-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4667d-128">InvalidUnfocused</span></span>|<span data-ttu-id="4667d-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4667d-129">ValidationStates</span></span>|<span data-ttu-id="4667d-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip değil.</span><span class="sxs-lookup"><span data-stu-id="4667d-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="4667d-131">ScrollViewer ControlTemplate Örneği</span><span class="sxs-lookup"><span data-stu-id="4667d-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="4667d-132">Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.ScrollViewer> denetim.</span><span class="sxs-lookup"><span data-stu-id="4667d-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="4667d-133">Önceki örnekte, bir veya daha fazla aşağıdaki kaynakları kullanır.</span><span class="sxs-lookup"><span data-stu-id="4667d-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4667d-134">Tam bir örnek için bkz: [ControlTemplates örneği ile stil oluşturma](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="4667d-134">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4667d-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4667d-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="4667d-136">Denetim stilleri ve şablonları</span><span class="sxs-lookup"><span data-stu-id="4667d-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="4667d-137">Denetim özelleştirme</span><span class="sxs-lookup"><span data-stu-id="4667d-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="4667d-138">Stil ve şablon oluşturma</span><span class="sxs-lookup"><span data-stu-id="4667d-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="4667d-139">ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme</span><span class="sxs-lookup"><span data-stu-id="4667d-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)