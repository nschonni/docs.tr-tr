---
title: "&#39; teki WPF sürüm 4. 5'deki yenilikler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
caps.latest.revision: "55"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4dc6a35a0ff8586b91ab7d74abc182fa6002f88
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="what39s-new-in-wpf-version-45"></a><span data-ttu-id="3d57a-102">&#39; teki WPF sürüm 4. 5'deki yenilikler</span><span class="sxs-lookup"><span data-stu-id="3d57a-102">What&#39;s New in WPF Version 4.5</span></span>
<span data-ttu-id="3d57a-103"><a name="introduction"></a>Bu konu, yeni ve geliştirilmiş özellikler hakkında bilgi içerir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sürüm 4.5.</span><span class="sxs-lookup"><span data-stu-id="3d57a-103"><a name="introduction"></a> This topic contains information about new and enhanced features in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] version 4.5.</span></span>  
  
 <span data-ttu-id="3d57a-104">Bu konu aşağıdaki bölümleri içermektedir:</span><span class="sxs-lookup"><span data-stu-id="3d57a-104">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="3d57a-105">Şerit denetimi</span><span class="sxs-lookup"><span data-stu-id="3d57a-105">Ribbon control</span></span>](#ribbon_control)  
  
-   [<span data-ttu-id="3d57a-106">Büyük görüntülerken, Gelişmiş performans gruplandırılmış veri kümelerini</span><span class="sxs-lookup"><span data-stu-id="3d57a-106">Improved performance when displaying large sets of grouped data</span></span>](#grouped_virtualization)  
  
-   [<span data-ttu-id="3d57a-107">VirtualizingPanel için yeni özellikler</span><span class="sxs-lookup"><span data-stu-id="3d57a-107">New features for the VirtualizingPanel</span></span>](#VirtualizingPanel)  
  
-   [<span data-ttu-id="3d57a-108">Statik özellikler bağlama</span><span class="sxs-lookup"><span data-stu-id="3d57a-108">Binding to static properties</span></span>](#static_properties)  
  
-   [<span data-ttu-id="3d57a-109">Koleksiyonlar üzerinde dışı kullanıcı Arabirimi iş parçacığı erişme</span><span class="sxs-lookup"><span data-stu-id="3d57a-109">Accessing collections on non-UI Threads</span></span>](#xthread_access)  
  
-   [<span data-ttu-id="3d57a-110">Zaman uyumlu ve zaman uyumsuz olarak verileri doğrulama</span><span class="sxs-lookup"><span data-stu-id="3d57a-110">Synchronously and Asynchronously validating data</span></span>](#INotifyDataErrorInfo)  
  
-   [<span data-ttu-id="3d57a-111">Veri bağlama kaynağını otomatik olarak güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="3d57a-111">Automatically updating the source of a data binding</span></span>](#delay)  
  
-   [<span data-ttu-id="3d57a-112">Bu uygulama ICustomTypeProvider türlerine bağlama</span><span class="sxs-lookup"><span data-stu-id="3d57a-112">Binding to types that Implement ICustomTypeProvider</span></span>](#ICustomTypeProvider)  
  
-   [<span data-ttu-id="3d57a-113">Bir bağlama ifadesinden veri bağlama bilgileri alınıyor</span><span class="sxs-lookup"><span data-stu-id="3d57a-113">Retrieving data binding information from a binding expression</span></span>](#binding_state)  
  
-   [<span data-ttu-id="3d57a-114">İçin geçerli bir DataContext nesne denetleniyor</span><span class="sxs-lookup"><span data-stu-id="3d57a-114">Checking for a valid DataContext object</span></span>](#DisconnectedSource)  
  
-   [<span data-ttu-id="3d57a-115">(Dinamik şekillendirme) verinin değerleri değiştirmek gibi veri yeniden konumlandırma</span><span class="sxs-lookup"><span data-stu-id="3d57a-115">Repositioning data as the data's values change (Live shaping)</span></span>](#live_shaping)  
  
-   [<span data-ttu-id="3d57a-116">Bir olay zayıf başvuru oluşturma için geliştirilmiş destek</span><span class="sxs-lookup"><span data-stu-id="3d57a-116">Improved Support for Establishing a Weak Reference to an Event</span></span>](#weak_event_pattern)  
  
-   [<span data-ttu-id="3d57a-117">Dağıtıcı sınıfı için yeni yöntemler</span><span class="sxs-lookup"><span data-stu-id="3d57a-117">New methods for the Dispatcher class</span></span>](#async)  
  
-   [<span data-ttu-id="3d57a-118">Olaylar için işaretleme uzantıları</span><span class="sxs-lookup"><span data-stu-id="3d57a-118">Markup Extensions for Events</span></span>](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a><span data-ttu-id="3d57a-119">Şerit denetimi</span><span class="sxs-lookup"><span data-stu-id="3d57a-119">Ribbon control</span></span>  
 <span data-ttu-id="3d57a-120">WPF 4.5 ile birlikte gelen bir <xref:System.Windows.Controls.Ribbon.Ribbon> hızlı erişim araç çubuğu, uygulama menüsü ve sekmeleri barındıran denetim.</span><span class="sxs-lookup"><span data-stu-id="3d57a-120">WPF 4.5 ships with a <xref:System.Windows.Controls.Ribbon.Ribbon> control that hosts a Quick Access Toolbar, Application Menu, and tabs.</span></span>  <span data-ttu-id="3d57a-121">Daha fazla bilgi için bkz: [Şerite Genel Bakış](/visualstudio/vsto/ribbon-overview).</span><span class="sxs-lookup"><span data-stu-id="3d57a-121">For more information, see the [Ribbon Overview](/visualstudio/vsto/ribbon-overview).</span></span>  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a><span data-ttu-id="3d57a-122">Büyük görüntülerken, Gelişmiş performans gruplandırılmış veri kümelerini</span><span class="sxs-lookup"><span data-stu-id="3d57a-122">Improved performance when displaying large sets of grouped data</span></span>  
 <span data-ttu-id="3d57a-123">UI sanallaştırma oluşur alt kullanıcı arabirimi (UI) öğeleri çok sayıda veri öğeleri hangi öğelerin ekranda görünür olan bağlı olarak oluşturulan.</span><span class="sxs-lookup"><span data-stu-id="3d57a-123">UI virtualization occurs when  a subset of user interface (UI) elements are generated from a larger number of data items based on which items are visible on the screen.</span></span> <span data-ttu-id="3d57a-124"><xref:System.Windows.Controls.VirtualizingPanel> Tanımlar <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> UI sanallaştırma için gruplandırılmış veri sağlayan özelliği eklenmiş.</span><span class="sxs-lookup"><span data-stu-id="3d57a-124">The <xref:System.Windows.Controls.VirtualizingPanel> defines the <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> attached property that enables UI Virtualization for grouped data.</span></span>  <span data-ttu-id="3d57a-125">Gruplandırma veriler hakkında daha fazla bilgi için bkz: nasıl yapılır: sıralama ve grup verilerini kullanan XAML görünümünde.</span><span class="sxs-lookup"><span data-stu-id="3d57a-125">For more information about grouping data, see How to: Sort and Group Data Using a View in XAML.</span></span>  <span data-ttu-id="3d57a-126">Gruplandırılmış veriler sanallaştırma hakkında daha fazla bilgi için bkz: <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> özelliği eklenmiş.</span><span class="sxs-lookup"><span data-stu-id="3d57a-126">For more information about virtualizing grouped data, see the <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> attached property.</span></span>  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a><span data-ttu-id="3d57a-127">VirtualizingPanel için yeni özellikler</span><span class="sxs-lookup"><span data-stu-id="3d57a-127">New features for the VirtualizingPanel</span></span>  
  
1.  <span data-ttu-id="3d57a-128">Belirleyebileceğiniz olup bir <xref:System.Windows.Controls.VirtualizingPanel>, gibi <xref:System.Windows.Controls.VirtualizingStackPanel>, kısmi öğeleri kullanarak görüntüler <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> özelliği eklenmiş.</span><span class="sxs-lookup"><span data-stu-id="3d57a-128">You can specify whether a <xref:System.Windows.Controls.VirtualizingPanel>, such as the <xref:System.Windows.Controls.VirtualizingStackPanel>, displays partial items by using the <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> attached property.</span></span> <span data-ttu-id="3d57a-129">Varsa <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> ayarlanır <xref:System.Windows.Controls.ScrollUnit.Item>, <xref:System.Windows.Controls.VirtualizingPanel> tamamen görünür olan öğeleri yalnızca görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-129">If <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> is set to <xref:System.Windows.Controls.ScrollUnit.Item>, the <xref:System.Windows.Controls.VirtualizingPanel> will only display items that are completely visible.</span></span> <span data-ttu-id="3d57a-130">Varsa <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> ayarlanır <xref:System.Windows.Controls.ScrollUnit.Pixel>, <xref:System.Windows.Controls.VirtualizingPanel> kısmen görünür öğeleri görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-130">If <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> is set to <xref:System.Windows.Controls.ScrollUnit.Pixel>, the <xref:System.Windows.Controls.VirtualizingPanel> can display partially visible items.</span></span>  
  
2.  <span data-ttu-id="3d57a-131">Önbellek boyutunu önce ve sonra Görünüm penceresinin belirtebilirsiniz zaman <xref:System.Windows.Controls.VirtualizingPanel> kullanarak sanallaştırılmasını <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> özelliği eklenmiş.</span><span class="sxs-lookup"><span data-stu-id="3d57a-131">You can specify the  size of the cache before and after the viewport when the <xref:System.Windows.Controls.VirtualizingPanel> is virtualizing by using the <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> attached property.</span></span>  <span data-ttu-id="3d57a-132">Önbellek alanı öğeleri değil sanallaştırılan görünüm penceresinin altında veya üstünde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-132">The cache is the amount of space above or below the viewport in which items are not virtualized.</span></span>  <span data-ttu-id="3d57a-133">Görünüme kaydırılan gibi kullanıcı Arabirimi öğeleri oluşturulmasını önlemek için bir önbellek kullanma performansını iyileştirebilir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-133">Using a cache to avoid generating UI elements as they’re scrolled into view can improve performance.</span></span> <span data-ttu-id="3d57a-134">Böylece uygulama işlemi sırasında yanıt vermemeye değil önbellek daha düşük öncelikli olarak doldurulur.</span><span class="sxs-lookup"><span data-stu-id="3d57a-134">The cache is populated at a lower priority so that the application does not become unresponsive during the operation.</span></span> <span data-ttu-id="3d57a-135"><xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> Özelliği tarafından kullanılan ölçü belirler <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-135">The <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> property determines the unit of measurement that is used by <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.</span></span>  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a><span data-ttu-id="3d57a-136">Statik özellikler bağlama</span><span class="sxs-lookup"><span data-stu-id="3d57a-136">Binding to static properties</span></span>  
 <span data-ttu-id="3d57a-137">Statik özellikler veri bağlama kaynağı olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-137">You can use static properties as the source of a data binding.</span></span> <span data-ttu-id="3d57a-138">Statik bir olay oluşursa özelliğin değeri değiştiğinde veri bağlama altyapısı tanır.</span><span class="sxs-lookup"><span data-stu-id="3d57a-138">The data binding engine recognizes when the property's value changes if a static event is raised.</span></span>  <span data-ttu-id="3d57a-139">Örneğin, varsa sınıfı `SomeClass` adlı bir statik özellik tanımlar `MyProperty`, `SomeClass` olan statik bir olay tanımlayabilirsiniz ne zaman yükseltilmiş değerini `MyProperty` değişiklikler.</span><span class="sxs-lookup"><span data-stu-id="3d57a-139">For example, if the class `SomeClass` defines a static property called `MyProperty`, `SomeClass` can define a static event that is raised when the value of `MyProperty` changes.</span></span>  <span data-ttu-id="3d57a-140">Statik olay aşağıdaki imzalar birini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-140">The static event can use either of the following signatures.</span></span>  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 <span data-ttu-id="3d57a-141">İlk durumda adlı statik bir olay sınıfı gösterir Not *PropertyName* `Changed` geçen <xref:System.EventArgs> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="3d57a-141">Note that in the first case, the class exposes a static event named *PropertyName*`Changed` that passes <xref:System.EventArgs> to the event handler.</span></span>  <span data-ttu-id="3d57a-142">İkinci durumda, adlı statik bir olay sınıfı gösterir `StaticPropertyChanged` geçen <xref:System.ComponentModel.PropertyChangedEventArgs> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="3d57a-142">In the second case, the class exposes a static event named `StaticPropertyChanged` that passes <xref:System.ComponentModel.PropertyChangedEventArgs> to the event handler.</span></span> <span data-ttu-id="3d57a-143">Statik özelliği uygulayan bir sınıf, her iki yöntemi kullanarak özellik değişikliği bildirimleri yükseltmek seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-143">A class that implements the static property can choose to raise property-change notifications using either method.</span></span>  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a><span data-ttu-id="3d57a-144">Koleksiyonlar üzerinde dışı kullanıcı Arabirimi iş parçacığı erişme</span><span class="sxs-lookup"><span data-stu-id="3d57a-144">Accessing collections on non-UI Threads</span></span>  
 <span data-ttu-id="3d57a-145">WPF erişmek ve iş parçacıkları koleksiyonu oluşturduğunuzda farklı veri koleksiyonlarında değiştirmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d57a-145">WPF enables you to access and modify data collections on threads other than the one that created the collection.</span></span>  <span data-ttu-id="3d57a-146">Bu bir veritabanı gibi bir dış kaynaktan veri almak ve kullanıcı Arabirimi iş parçacığı üzerinde verileri görüntülemek için bir arka plan iş parçacığı kullanmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d57a-146">This enables you to use a background thread to receive data from an external source, such as a database, and display the data on the UI thread.</span></span>  <span data-ttu-id="3d57a-147">Koleksiyon değiştirmek için başka bir iş parçacığı kullanarak, kullanıcı arabiriminiz için kullanıcı etkileşimi yanıt verebilecek duruma gelir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-147">By using another thread to modify the collection, your user interface remains responsive to user interaction.</span></span>  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a><span data-ttu-id="3d57a-148">Zaman uyumlu ve zaman uyumsuz olarak verileri doğrulama</span><span class="sxs-lookup"><span data-stu-id="3d57a-148">Synchronously and Asynchronously validating data</span></span>  
 <span data-ttu-id="3d57a-149"><xref:System.ComponentModel.INotifyDataErrorInfo> Arabirimi özel doğrulama kuralları uygulamak ve doğrulama sonuçlarını zaman uyumsuz olarak kullanıma sunmak veri sınıflar sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d57a-149">The <xref:System.ComponentModel.INotifyDataErrorInfo> interface enables data entity classes to implement custom validation rules and expose validation results asynchronously.</span></span> <span data-ttu-id="3d57a-150">Bu arabirim, özel hata nesneleri, özellik, çapraz özelliği hataları ve varlık düzeyi hataları başına birden çok hata da destekler.</span><span class="sxs-lookup"><span data-stu-id="3d57a-150">This interface also supports custom error objects, multiple errors per property, cross-property errors, and entity-level errors.</span></span>  <span data-ttu-id="3d57a-151">Daha fazla bilgi için bkz. <xref:System.ComponentModel.INotifyDataErrorInfo>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-151">For more information, see <xref:System.ComponentModel.INotifyDataErrorInfo>.</span></span>  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a><span data-ttu-id="3d57a-152">Veri bağlama kaynağını otomatik olarak güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="3d57a-152">Automatically updating the source of a data binding</span></span>  
 <span data-ttu-id="3d57a-153">Bir veri kaynağını güncelleştirmek için bir veri bağlama kullanırsanız, kullanabileceğiniz <xref:System.Windows.Data.BindingBase.Delay%2A> özelliği bir özellik değişikliklerinden sonra kaynak güncelleştirmelerinin önce hedefte geçirmek için zaman miktarı belirtin.</span><span class="sxs-lookup"><span data-stu-id="3d57a-153">If you use a data binding to update a data source, you can use the <xref:System.Windows.Data.BindingBase.Delay%2A> property to specify an amount of time to pass after the property changes on the target before the source updates.</span></span>  <span data-ttu-id="3d57a-154">Örneğin, sahip olduğunuzu varsayın bir <xref:System.Windows.Controls.Slider> olan kendi <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> özelliği veri iki yönlü bir veri nesnesi özelliğine bağlı ve <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> özelliği ayarlanmış <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-154">For example, suppose that you have a <xref:System.Windows.Controls.Slider> that has its <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property data two-way bound to a property of a data object and the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  <span data-ttu-id="3d57a-155">Bu örnekte, kullanıcı taşıdığında <xref:System.Windows.Controls.Slider>, her piksel için kaynak güncelleştirmeleri, <xref:System.Windows.Controls.Slider> taşır.</span><span class="sxs-lookup"><span data-stu-id="3d57a-155">In this example, when the user moves the <xref:System.Windows.Controls.Slider>, the source updates for each pixel that the <xref:System.Windows.Controls.Slider> moves.</span></span>  <span data-ttu-id="3d57a-156">Kaynak nesne genellikle kaydırıcının değer, yalnızca kaydırıcının <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> değiştirme durdurur.</span><span class="sxs-lookup"><span data-stu-id="3d57a-156">The source object typically needs the value of the slider only when the slider's <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> stops changing.</span></span>  <span data-ttu-id="3d57a-157">Kaynak çok sık güncelleştirilmesini önlemek için kullanmak <xref:System.Windows.Data.BindingBase.Delay%2A> taşıma kaydırma kestikten sonra belirli bir süre sona erdiğinde kadar'ın kaynak güncellenmemelidir belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="3d57a-157">To prevent updating the source too often, use <xref:System.Windows.Data.BindingBase.Delay%2A> to specify that the source should not be updated until a certain amount of time elapses after the thumb stops moving.</span></span>  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a><span data-ttu-id="3d57a-158">Bu uygulama ICustomTypeProvider türlerine bağlama</span><span class="sxs-lookup"><span data-stu-id="3d57a-158">Binding to types that Implement ICustomTypeProvider</span></span>  
 <span data-ttu-id="3d57a-159">WPF veri bağlama uygulayan nesneler için destekleyen <xref:System.Reflection.ICustomTypeProvider>, özel türleri olarak da bilinir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-159">WPF supports data binding to objects that implement <xref:System.Reflection.ICustomTypeProvider>, also known as custom types.</span></span>  <span data-ttu-id="3d57a-160">Aşağıdaki durumlarda özel türler kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-160">You can use custom types in the following cases.</span></span>  
  
1.  <span data-ttu-id="3d57a-161">Farklı bir <xref:System.Windows.PropertyPath> Veri bağlamada.</span><span class="sxs-lookup"><span data-stu-id="3d57a-161">As a <xref:System.Windows.PropertyPath> in a data binding.</span></span> <span data-ttu-id="3d57a-162">Örneğin, <xref:System.Windows.Data.Binding.Path%2A> özelliği bir <xref:System.Windows.Data.Binding> özel türünde bir özellik başvuruda bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-162">For example, the <xref:System.Windows.Data.Binding.Path%2A> property of a <xref:System.Windows.Data.Binding> can reference a property of a custom type.</span></span>  
  
2.  <span data-ttu-id="3d57a-163">Değeri olarak <xref:System.Windows.DataTemplate.DataType%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="3d57a-163">As the value of the <xref:System.Windows.DataTemplate.DataType%2A> property.</span></span>  
  
3.  <span data-ttu-id="3d57a-164">Otomatik oluşturulan sütunları belirleyen bir tür olarak bir <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-164">As a type that determines the automatically generated columns in a <xref:System.Windows.Controls.DataGrid>.</span></span>  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a><span data-ttu-id="3d57a-165">Bir bağlama ifadesinden veri bağlama bilgileri alınıyor</span><span class="sxs-lookup"><span data-stu-id="3d57a-165">Retrieving data binding information from a binding expression</span></span>  
 <span data-ttu-id="3d57a-166">Bazı durumlarda, alabilirsiniz <xref:System.Windows.Data.BindingExpression> , bir <xref:System.Windows.Data.Binding> ve bağlama kaynak ve hedef nesneler hakkında bilgi gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="3d57a-166">In certain cases, you might get the <xref:System.Windows.Data.BindingExpression> of a <xref:System.Windows.Data.Binding> and need information about the source and target objects of the binding.</span></span>  <span data-ttu-id="3d57a-167">Kaynak veya hedef nesne veya ilişkili özelliği etkinleştirmek için yeni API'ler eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-167">New APIs have been added to enable you to get the source or target object or the associated property.</span></span>  <span data-ttu-id="3d57a-168">Olduğunda, bir <xref:System.Windows.Data.BindingExpression>, hedef ve kaynak hakkında bilgi almak için aşağıdaki API'leri kullanın.</span><span class="sxs-lookup"><span data-stu-id="3d57a-168">When you have a <xref:System.Windows.Data.BindingExpression>, use the following APIs to get information about the target and source.</span></span>  
  
|<span data-ttu-id="3d57a-169">Bağlamanın bu değeri bulmak için</span><span class="sxs-lookup"><span data-stu-id="3d57a-169">To find this value of the binding</span></span>|<span data-ttu-id="3d57a-170">Bu API kullanın</span><span class="sxs-lookup"><span data-stu-id="3d57a-170">Use this API</span></span>|  
|---------------------------------------|------------------|  
|<span data-ttu-id="3d57a-171">Hedef nesne</span><span class="sxs-lookup"><span data-stu-id="3d57a-171">The target object</span></span>|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3d57a-172">Target özelliği</span><span class="sxs-lookup"><span data-stu-id="3d57a-172">The target property</span></span>|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3d57a-173">Kaynak nesnesi</span><span class="sxs-lookup"><span data-stu-id="3d57a-173">The source object</span></span>|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3d57a-174">Source özelliği</span><span class="sxs-lookup"><span data-stu-id="3d57a-174">The source property</span></span>|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3d57a-175">Olup olmadığını <xref:System.Windows.Data.BindingExpression> ait bir<xref:System.Windows.Data.BindingGroup></span><span class="sxs-lookup"><span data-stu-id="3d57a-175">Whether the <xref:System.Windows.Data.BindingExpression> belongs to a <xref:System.Windows.Data.BindingGroup></span></span>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3d57a-176">Sahibi bir<xref:System.Windows.Data.BindingGroup></span><span class="sxs-lookup"><span data-stu-id="3d57a-176">The owner of a <xref:System.Windows.Data.BindingGroup></span></span>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a><span data-ttu-id="3d57a-177">İçin geçerli bir DataContext nesne denetleniyor</span><span class="sxs-lookup"><span data-stu-id="3d57a-177">Checking for a valid DataContext object</span></span>  
 <span data-ttu-id="3d57a-178">Durumlar vardır nerede <xref:System.Windows.FrameworkElement.DataContext%2A> bir öğe kapsayıcı bir <xref:System.Windows.Controls.ItemsControl> bağlantısı kesiliyor.</span><span class="sxs-lookup"><span data-stu-id="3d57a-178">There are cases where the <xref:System.Windows.FrameworkElement.DataContext%2A> of an item container in an <xref:System.Windows.Controls.ItemsControl> becomes disconnected.</span></span>  <span data-ttu-id="3d57a-179">Bir öğe kapsayıcı bir öğeyi görüntüleyen UI öğedir bir <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-179">An item container is the UI element that displays an item in an <xref:System.Windows.Controls.ItemsControl>.</span></span>  <span data-ttu-id="3d57a-180">Zaman bir <xref:System.Windows.Controls.ItemsControl> veriler bir koleksiyona bağlı, bir öğe kapsayıcısı her öğe için oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3d57a-180">When an <xref:System.Windows.Controls.ItemsControl> is data bound to a collection, an item container is generated for each item.</span></span> <span data-ttu-id="3d57a-181">Bazı durumlarda, öğe kapsayıcılarını görsel ağaç kaldırılır.</span><span class="sxs-lookup"><span data-stu-id="3d57a-181">In some cases, item containers are removed from the visual tree.</span></span> <span data-ttu-id="3d57a-182">Burada bir öğe kapsayıcısı kaldırılır iki tipik örnekleridir olan bir öğe temel alınan koleksiyonundan zaman kaldırılır ve sanallaştırma üzerinde etkin olduğunda <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-182">Two typical cases where an item container is removed are when an item is removed from the underlying collection and when virtualization is enabled on the <xref:System.Windows.Controls.ItemsControl>.</span></span> <span data-ttu-id="3d57a-183">Bu durumda, <xref:System.Windows.FrameworkElement.DataContext%2A> öğe kapsayıcısı özelliği tarafından döndürülen sentinel nesnesine ayarlanacak <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> statik özelliği.</span><span class="sxs-lookup"><span data-stu-id="3d57a-183">In these cases, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the item container will be set to the sentinel object that is returned by the <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> static property.</span></span>  <span data-ttu-id="3d57a-184">Denetlemelisiniz olup olmadığını <xref:System.Windows.FrameworkElement.DataContext%2A> eşittir <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> erişmeden önce nesne <xref:System.Windows.FrameworkElement.DataContext%2A> bir öğe kapsayıcısı.</span><span class="sxs-lookup"><span data-stu-id="3d57a-184">You should check whether the <xref:System.Windows.FrameworkElement.DataContext%2A> is equal to the <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> object before accessing the <xref:System.Windows.FrameworkElement.DataContext%2A> of an item container.</span></span>  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a><span data-ttu-id="3d57a-185">(Dinamik şekillendirme) verinin değerleri değiştirmek gibi veri yeniden konumlandırma</span><span class="sxs-lookup"><span data-stu-id="3d57a-185">Repositioning data as the data's values change (Live shaping)</span></span>  
 <span data-ttu-id="3d57a-186">Veri koleksiyonunu gruplandırılmış, sıralanmış, filtre veya kaldırılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d57a-186">A collection of data can be grouped, sorted, or filtered.</span></span> <span data-ttu-id="3d57a-187">WPF 4.5 veri değiştirildiğinde düzenlenmeyecek veri sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d57a-187">WPF 4.5 enables the data to be rearranged when the data is modified.</span></span> <span data-ttu-id="3d57a-188">Örneğin, bir uygulama kullandığını varsayın bir <xref:System.Windows.Controls.DataGrid> listelemek için hisse senedi stoklar ve hisse stok değerine göre sıralanır.</span><span class="sxs-lookup"><span data-stu-id="3d57a-188">For example, suppose that an application uses a <xref:System.Windows.Controls.DataGrid> to list stocks in a stock market and the stocks are sorted by stock value.</span></span> <span data-ttu-id="3d57a-189">Canlı sıralama hisse üzerinde etkinse, <xref:System.Windows.Data.CollectionView>, stok 's konumda <xref:System.Windows.Controls.DataGrid> hisse senedi değeri büyük hale geldiğinde taşır veya değerinden başka bir stok 's değeri.</span><span class="sxs-lookup"><span data-stu-id="3d57a-189">If live sorting is enabled on the stocks' <xref:System.Windows.Data.CollectionView>, a stock's position in the <xref:System.Windows.Controls.DataGrid> moves when the value of the stock becomes greater or less than another stock's value.</span></span>   <span data-ttu-id="3d57a-190">Daha fazla bilgi için bkz: <xref:System.ComponentModel.ICollectionViewLiveShaping> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="3d57a-190">For more information, see the <xref:System.ComponentModel.ICollectionViewLiveShaping> interface.</span></span>  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a><span data-ttu-id="3d57a-191">Bir olay zayıf başvuru oluşturma için geliştirilmiş destek</span><span class="sxs-lookup"><span data-stu-id="3d57a-191">Improved Support for Establishing a Weak Reference to an Event</span></span>  
 <span data-ttu-id="3d57a-192">Olayları abonelere içinde ek arabirimi uygulama olmadan katılabilmesi için zayıf olay düzeni uygulama artık daha kolay olur.</span><span class="sxs-lookup"><span data-stu-id="3d57a-192">Implementing the weak event pattern is now easier because subscribers to events can participate in it without implementing an extra interface.</span></span>  <span data-ttu-id="3d57a-193">Genel <xref:System.Windows.WeakEventManager> sınıfı ayrıca ayrılmış bir varsa zayıf olay desende katılmayı aboneleri sağlar <xref:System.Windows.WeakEventManager> için belirli bir olay yok.</span><span class="sxs-lookup"><span data-stu-id="3d57a-193">The generic <xref:System.Windows.WeakEventManager> class also enables subscribers to participate in the weak event pattern if a dedicated <xref:System.Windows.WeakEventManager> does not exist for a certain event.</span></span>  <span data-ttu-id="3d57a-194">Daha fazla bilgi için bkz: [zayıf olay desenleri](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="3d57a-194">For more information, see [Weak Event Patterns](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).</span></span>  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a><span data-ttu-id="3d57a-195">Dağıtıcı sınıfı için yeni yöntemler</span><span class="sxs-lookup"><span data-stu-id="3d57a-195">New methods for the Dispatcher class</span></span>  
 <span data-ttu-id="3d57a-196">Dispatcher sınıfı zaman uyumlu ve zaman uyumsuz işlemleri için yeni yöntemleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="3d57a-196">The Dispatcher class defines new methods for synchronous and asynchronous operations.</span></span>  <span data-ttu-id="3d57a-197">Zaman uyumlu <xref:System.Windows.Threading.Dispatcher.Invoke%2A> yöntemi tanımlar Al aşırı bir <xref:System.Action> veya <xref:System.Func%601> parametresi.</span><span class="sxs-lookup"><span data-stu-id="3d57a-197">The synchronous <xref:System.Windows.Threading.Dispatcher.Invoke%2A> method defines overloads that take an <xref:System.Action> or <xref:System.Func%601> parameter.</span></span> <span data-ttu-id="3d57a-198">Yeni zaman uyumsuz yöntem <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, ayrıca alır bir <xref:System.Action> veya <xref:System.Func%601> döndürür ve geri çağırma parametresi olarak bir <xref:System.Windows.Threading.DispatcherOperation> veya <xref:System.Windows.Threading.DispatcherOperation%601>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-198">The new asynchronous method, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, also takes an <xref:System.Action> or <xref:System.Func%601> as the callback parameter and returns a <xref:System.Windows.Threading.DispatcherOperation> or <xref:System.Windows.Threading.DispatcherOperation%601>.</span></span>   <span data-ttu-id="3d57a-199"><xref:System.Windows.Threading.DispatcherOperation> Ve <xref:System.Windows.Threading.DispatcherOperation%601> sınıflarını tanımla bir <xref:System.Threading.Tasks.Task> özelliği.</span><span class="sxs-lookup"><span data-stu-id="3d57a-199">The <xref:System.Windows.Threading.DispatcherOperation> and <xref:System.Windows.Threading.DispatcherOperation%601> classes define a <xref:System.Threading.Tasks.Task> property.</span></span>  <span data-ttu-id="3d57a-200">Çağırdığınızda <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, kullanabileceğiniz `await` ya da anahtar sözcük <xref:System.Windows.Threading.DispatcherOperation> veya ilişkili <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="3d57a-200">When you call <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, you can use the `await` keyword with either the <xref:System.Windows.Threading.DispatcherOperation> or the associated <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="3d57a-201">Zaman uyumlu olarak bekleyin gerekiyorsa <xref:System.Threading.Tasks.Task> tarafından döndürülen bir <xref:System.Windows.Threading.DispatcherOperation> veya <xref:System.Windows.Threading.DispatcherOperation%601>, çağrı <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> genişletme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3d57a-201">If you need to wait synchronously for the <xref:System.Threading.Tasks.Task> that is returned by a <xref:System.Windows.Threading.DispatcherOperation> or <xref:System.Windows.Threading.DispatcherOperation%601>, call the <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> extension method.</span></span> <span data-ttu-id="3d57a-202">Çağırma <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> işlemi çağıran iş parçacığı üzerinde sıraya alınmış bir kilitlenmeyle neden olur.</span><span class="sxs-lookup"><span data-stu-id="3d57a-202">Calling <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> will result in a deadlock if the operation is queued on a calling thread.</span></span> <span data-ttu-id="3d57a-203">Kullanma hakkında daha fazla bilgi için bir <xref:System.Threading.Tasks.Task> zaman uyumsuz işlemleri gerçekleştirmek için bkz: [görev Paralelliği (görev paralel kitaplığı)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="3d57a-203">For more information about using a <xref:System.Threading.Tasks.Task> to perform asynchronous operations, see [Task Parallelism (Task Parallel Library)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a><span data-ttu-id="3d57a-204">Olaylar için işaretleme uzantıları</span><span class="sxs-lookup"><span data-stu-id="3d57a-204">Markup Extensions for Events</span></span>  
 <span data-ttu-id="3d57a-205">WPF 4.5 Biçimlendirme uzantıları olaylarını destekler.</span><span class="sxs-lookup"><span data-stu-id="3d57a-205">WPF 4.5 supports markup extensions for events.</span></span>  <span data-ttu-id="3d57a-206">WPF olayları için kullanılacak bir işaretleme uzantısı tanımlamaz, ancak üçüncü tarafların olaylarla kullanılabilecek biçimlendirme uzantısı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-206">While WPF does not define a markup extension to be used for events, third parties are able to create a markup extension that can be used with events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d57a-207">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3d57a-207">See Also</span></span>  
 [<span data-ttu-id="3d57a-208">.NET Framework’teki Yenilikler</span><span class="sxs-lookup"><span data-stu-id="3d57a-208">What's New in the .NET Framework</span></span>](../../../../docs/framework/whats-new/index.md)