---
title: "Nasıl yapılır: İlerleme Durumunu Gösteren Windows Forms Denetimi Oluşturma"
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
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55b3879b894658c9a649004348a198d004040af3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="503d4-102">Nasıl yapılır: İlerleme Durumunu Gösteren Windows Forms Denetimi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="503d4-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="503d4-103">Aşağıdaki kod örneğinde adlı özel bir denetim gösterilir `FlashTrackBar` kullanıcı düzeyinde veya uygulama ilerlemesini göstermek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="503d4-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="503d4-104">Gradyan ilerleme görsel olarak sunmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="503d4-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="503d4-105">`FlashTrackBar` Denetim aşağıdaki kavramlar gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="503d4-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
-   <span data-ttu-id="503d4-106">Özel özellikler tanımlama.</span><span class="sxs-lookup"><span data-stu-id="503d4-106">Defining custom properties.</span></span>  
  
-   <span data-ttu-id="503d4-107">Özel olaylar tanımlama.</span><span class="sxs-lookup"><span data-stu-id="503d4-107">Defining custom events.</span></span> <span data-ttu-id="503d4-108">(`FlashTrackBar` tanımlar `ValueChanged` olay.)</span><span class="sxs-lookup"><span data-stu-id="503d4-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
-   <span data-ttu-id="503d4-109">Geçersiz kılma <xref:System.Windows.Forms.Control.OnPaint%2A> denetimi çizmek için mantığın yöntemi.</span><span class="sxs-lookup"><span data-stu-id="503d4-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
-   <span data-ttu-id="503d4-110">Alan kullanarak denetim çizim için kullanılabilir bilgi işlem kendi <xref:System.Windows.Forms.Control.ClientRectangle%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="503d4-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="503d4-111">`FlashTrackBar`bunu yapar, `OptimizedInvalidate` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="503d4-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
-   <span data-ttu-id="503d4-112">Windows Forms Tasarımcısı'nda değiştirildiğinde serileştirme ya da kalıcılığı bir özellik için uygulama.</span><span class="sxs-lookup"><span data-stu-id="503d4-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="503d4-113">`FlashTrackBar`tanımlar `ShouldSerializeStartColor` ve `ShouldSerializeEndColor` seri hale getirme yöntemleri kendi `StartColor` ve `EndColor` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="503d4-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="503d4-114">Tarafından tanımlanan özel özellikler aşağıdaki tabloda gösterilmektedir `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="503d4-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="503d4-115">Özellik</span><span class="sxs-lookup"><span data-stu-id="503d4-115">Property</span></span>|<span data-ttu-id="503d4-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="503d4-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="503d4-117">Kullanıcı tıklatıp sürükleyerek flash izleme çubuğu değerini değiştirebilir olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="503d4-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="503d4-118">İzleme çubuğu Bitiş rengini belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="503d4-119">Ön plan gradyan göre arka plan koyu için ne kadar belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="503d4-120">İzleme çubuğu en büyük değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="503d4-121">İzleme çubuğu en küçük değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="503d4-122">Geçişin başlangıç rengini belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="503d4-123">Yüzde geçişin görüntülenip görüntülenmeyeceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="503d4-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="503d4-124">Geçerli değeri geçişin görüntülenip görüntülenmeyeceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="503d4-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="503d4-125">İzleme çubuğu geçerli değerini gösteren bir renk gradyan görüntüleyip görüntülemeyeceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="503d4-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="503d4-126">İzleme çubuğu geçerli değeri belirtir.</span><span class="sxs-lookup"><span data-stu-id="503d4-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="503d4-127">Aşağıdaki tabloda ek üyeleri tarafından tanımlanan gösterilmektedir `FlashTrackBar:` özellik değişti olayı ve olayını yöntemi.</span><span class="sxs-lookup"><span data-stu-id="503d4-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="503d4-128">Üye</span><span class="sxs-lookup"><span data-stu-id="503d4-128">Member</span></span>|<span data-ttu-id="503d4-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="503d4-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="503d4-130">Olan olay zaman yükseltilmiş `Value` çubuğu değişiklikleri izleme özelliği.</span><span class="sxs-lookup"><span data-stu-id="503d4-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="503d4-131">Başlatır yöntemi `ValueChanged` olay.</span><span class="sxs-lookup"><span data-stu-id="503d4-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="503d4-132">`FlashTrackBar`kullanan <xref:System.EventArgs> olay verileri için sınıf ve <xref:System.EventHandler> olay temsilci için.</span><span class="sxs-lookup"><span data-stu-id="503d4-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="503d4-133">Karşılık gelen işlemek için *EventName* olayları `FlashTrackBar` öğesinden devralınan aşağıdaki yöntemlerini geçersiz kılar <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="503d4-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="503d4-134">Karşılık gelen özellik değişti olayları işlemek için `FlashTrackBar` öğesinden devralınan aşağıdaki yöntemlerini geçersiz kılar <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="503d4-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="503d4-135">Örnek</span><span class="sxs-lookup"><span data-stu-id="503d4-135">Example</span></span>  
 <span data-ttu-id="503d4-136">`FlashTrackBar` Denetim tanımlayan iki UI türü düzenleyici `FlashTrackBarValueEditor` ve `FlashTrackBarDarkenByEditor`, aşağıdaki kod listesinde gösterilir.</span><span class="sxs-lookup"><span data-stu-id="503d4-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="503d4-137">`HostApp` Sınıfını kullanan `FlashTrackBar` bir Windows formunda denetimi.</span><span class="sxs-lookup"><span data-stu-id="503d4-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="503d4-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="503d4-138">See Also</span></span>  
 [<span data-ttu-id="503d4-139">Tasarım zamanı desteği genişletme</span><span class="sxs-lookup"><span data-stu-id="503d4-139">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="503d4-140">Windows Forms denetimi geliştirmenin esasları</span><span class="sxs-lookup"><span data-stu-id="503d4-140">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)