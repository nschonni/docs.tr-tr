---
title: "Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e39a8df5c8aee05414e778f15a29bbeda8dba930
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="27435-102">Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma</span><span class="sxs-lookup"><span data-stu-id="27435-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="27435-103">.NET Framework kullanabilirsiniz [taşınabilir sınıf kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Model-görünüm-görünüm Model (MVVM) desen uygulamak ve birden çok platform genelinde derlemeleri paylaşmak için.</span><span class="sxs-lookup"><span data-stu-id="27435-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  
  
 <span data-ttu-id="27435-104">MVVM temel iş mantığı kullanıcı arabiriminden yalıtan bir uygulama düzeni ' dir.</span><span class="sxs-lookup"><span data-stu-id="27435-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="27435-105">Model ve görünüm modeli sınıflarda uygulayabileceğiniz bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]ve ardından farklı platform için özelleştirilmiş görünümler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="27435-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="27435-106">Bu yaklaşım, veri yazmak sağlar modeli ve yalnızca bir kez iş mantığı ve .NET Framework, Silverlight, Windows Phone kod kullanımı ve [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aşağıdaki çizimde gösterildiği gibi uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="27435-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="27435-107">![Diyagram MVVM ile taşınabilir](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="27435-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="27435-108">Bu konuda MVVM desen hakkında genel bilgi sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="27435-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="27435-109">Yalnızca nasıl kullanılacağı hakkında bilgi sağlar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] MVVM uygulamak için.</span><span class="sxs-lookup"><span data-stu-id="27435-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="27435-110">MVVM hakkında daha fazla bilgi için bkz: [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span><span class="sxs-lookup"><span data-stu-id="27435-110">For more information about MVVM, see the [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="27435-111">MVVM destekleyen sınıfları</span><span class="sxs-lookup"><span data-stu-id="27435-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="27435-112">Hedeflediğinizde [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight ya da için Windows Phone 7.5, [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje, aşağıdaki sınıflar MVVM desen uygulamak için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="27435-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="27435-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="27435-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="27435-123">Tüm sınıflarda <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> ad alanı</span><span class="sxs-lookup"><span data-stu-id="27435-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="27435-124">MVVM uygulama</span><span class="sxs-lookup"><span data-stu-id="27435-124">Implementing MVVM</span></span>  
 <span data-ttu-id="27435-125">MVVM uygulamak için genellikle model ve görünüm modeli oluşturduğunuz bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] , çünkü proje bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje taşınabilir olmayan proje başvuruda bulunamaz.</span><span class="sxs-lookup"><span data-stu-id="27435-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="27435-126">Model ve görünüm modeli ayrı projelerinde veya aynı projede olabilir.</span><span class="sxs-lookup"><span data-stu-id="27435-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="27435-127">Ayrı projeler kullanırsanız, bir başvuru görünüm model projeden modeli projeye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="27435-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="27435-128">Model derlemek ve model projeleri görüntüledikten sonra bu derlemelerde görünüm içeriyor uygulamasında başvuru.</span><span class="sxs-lookup"><span data-stu-id="27435-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="27435-129">Görünüm yalnızca görünüm model ile etkileşime giren, görünüm modeli içeren derleme başvurusu yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="27435-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="27435-130">Model</span><span class="sxs-lookup"><span data-stu-id="27435-130">Model</span></span>  
 <span data-ttu-id="27435-131">Aşağıdaki örnek, içinde yer alan bir Basitleştirilmiş model sınıfı gösterir. bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projesi.</span><span class="sxs-lookup"><span data-stu-id="27435-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="27435-132">Aşağıdaki örnek, doldurmak, almak ve verileri güncelleştirmek için basit bir yol gösterir. bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projesi.</span><span class="sxs-lookup"><span data-stu-id="27435-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="27435-133">Gerçek bir uygulamada, bir Windows Communication Foundation (WCF) hizmeti gibi bir kaynaktan veri almak.</span><span class="sxs-lookup"><span data-stu-id="27435-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="27435-134">Görünüm modeli</span><span class="sxs-lookup"><span data-stu-id="27435-134">View Model</span></span>  
 <span data-ttu-id="27435-135">Görünüm modelleri için temel sınıf sık MVVM deseni uygularken eklenir.</span><span class="sxs-lookup"><span data-stu-id="27435-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="27435-136">Aşağıdaki örnek, bir taban sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="27435-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="27435-137">Uygulaması <xref:System.Windows.Input.ICommand> arabirimi MVVM deseni sıkça kullanılır.</span><span class="sxs-lookup"><span data-stu-id="27435-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="27435-138">Aşağıdaki örnek uygulaması gösterir <xref:System.Windows.Input.ICommand> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="27435-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="27435-139">Aşağıdaki örnekte bir basitleştirilmiş görünüm modeli gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="27435-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="27435-140">Görüntüle</span><span class="sxs-lookup"><span data-stu-id="27435-140">View</span></span>  
 <span data-ttu-id="27435-141">Gelen bir [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] uygulama, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulaması, Silverlight tabanlı bir uygulamanın veya Windows Phone 7.5 uygulama, başvuru modeli ve görünüm modeli projeleri içeren derleme.</span><span class="sxs-lookup"><span data-stu-id="27435-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="27435-142">Ardından Görünüm model ile etkileşime giren bir görünüm oluşturun.</span><span class="sxs-lookup"><span data-stu-id="27435-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="27435-143">Aşağıdaki örnek alır ve görünüm modeli verileri güncelleştiren basitleştirilmiş bir Windows Presentation Foundation (WPF) uygulamasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="27435-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="27435-144">Silverlight, Windows Phone benzer görünümler oluşturabilir veya [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="27435-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="27435-145">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="27435-145">See Also</span></span>  
 [<span data-ttu-id="27435-146">Taşınabilir sınıf kitaplığı</span><span class="sxs-lookup"><span data-stu-id="27435-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)