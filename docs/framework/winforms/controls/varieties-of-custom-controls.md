---
title: "Özel Denetim Çeşitleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a8d858228630147e1fbcdfab6a52fba5a63a566
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="varieties-of-custom-controls"></a><span data-ttu-id="46237-102">Özel Denetim Çeşitleri</span><span class="sxs-lookup"><span data-stu-id="46237-102">Varieties of Custom Controls</span></span>
<span data-ttu-id="46237-103">.NET Framework ile geliştirme ve yeni denetimleri uygulayın.</span><span class="sxs-lookup"><span data-stu-id="46237-103">With the .NET Framework, you can develop and implement new controls.</span></span> <span data-ttu-id="46237-104">Devralma yoluyla da olarak mevcut denetimleri hakkında bilgi sahibi kullanıcı denetimi işlevselliğini genişletebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-104">You can extend the functionality of the familiar user control as well as existing controls through inheritance.</span></span> <span data-ttu-id="46237-105">Kendi boyama gerçekleştirmek özel denetimler de yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-105">You can also write custom controls that perform their own painting.</span></span>  
  
 <span data-ttu-id="46237-106">Hangi tür denetimi oluşturmak için kafa karıştırıcı olabilir karar verme.</span><span class="sxs-lookup"><span data-stu-id="46237-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="46237-107">Bu konuda çeşitli içinden denetimleri arasında devralabilirsiniz ve belirli bir tür denetimi projeniz için seçim yapma hakkında bilgi sağlar farklılıkları vurgular.</span><span class="sxs-lookup"><span data-stu-id="46237-107">This topic highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular kind of control for your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46237-108">Web Forms kullanmak için bir denetim yazma hakkında daha fazla bilgi için bkz: [özel ASP.NET sunucu denetimleri geliştirme](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span><span class="sxs-lookup"><span data-stu-id="46237-108">For information about authoring a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
  
## <a name="base-control-class"></a><span data-ttu-id="46237-109">Temel denetim sınıfı</span><span class="sxs-lookup"><span data-stu-id="46237-109">Base Control Class</span></span>  
 <span data-ttu-id="46237-110"><xref:System.Windows.Forms.Control> Sınıfı Windows Forms denetimleri için temel sınıfı olan.</span><span class="sxs-lookup"><span data-stu-id="46237-110">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="46237-111">Windows Forms uygulamalarında visual görüntülemek için gerekli altyapıyı sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-111">It provides the infrastructure required for visual display in Windows Forms applications.</span></span>  
  
 <span data-ttu-id="46237-112"><xref:System.Windows.Forms.Control> Sınıfı Windows Forms uygulamalarında görsel görüntü sağlamak için aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="46237-112">The <xref:System.Windows.Forms.Control> class performs the following tasks to provide visual display in Windows Forms applications:</span></span>  
  
-   <span data-ttu-id="46237-113">Bir pencere tanıtıcının kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="46237-113">Exposes a window handle.</span></span>  
  
-   <span data-ttu-id="46237-114">İleti yönlendirme yönetir.</span><span class="sxs-lookup"><span data-stu-id="46237-114">Manages message routing.</span></span>  
  
-   <span data-ttu-id="46237-115">Fare ve klavye olaylarının ve diğer birçok kullanıcı arabirimi olayları sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-115">Provides mouse and keyboard events, and many other user interface events.</span></span>  
  
-   <span data-ttu-id="46237-116">Gelişmiş Düzen özelliklerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-116">Provides advanced layout features.</span></span>  
  
-   <span data-ttu-id="46237-117">Birçok özelliği görsel görüntü için belirli gibi içeren <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, ve <xref:System.Windows.Forms.Control.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="46237-117">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>  
  
-   <span data-ttu-id="46237-118">Güvenlik ve Microsoft® ActiveX denetimi olarak davranacak şekilde bir Windows Forms denetimi için gerekli iş parçacığı oluşturma desteği sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-118">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>  
  
 <span data-ttu-id="46237-119">Çok altyapısının temel sınıfı tarafından sağlandığından, kendi Windows Forms denetimleri geliştirme oldukça kolaydır.</span><span class="sxs-lookup"><span data-stu-id="46237-119">Because so much of the infrastructure is provided by the base class, it is relatively easy to develop your own Windows Forms controls.</span></span>  
  
## <a name="kinds-of-controls"></a><span data-ttu-id="46237-120">Denetim türleri</span><span class="sxs-lookup"><span data-stu-id="46237-120">Kinds of Controls</span></span>  
 <span data-ttu-id="46237-121">Windows Forms denetimleri kullanıcı tanımlı üç tür destekler: *bileşik*, *Genişletilmiş*, ve *özel*.</span><span class="sxs-lookup"><span data-stu-id="46237-121">Windows Forms supports three kinds of user-defined controls: *composite*, *extended*, and *custom*.</span></span> <span data-ttu-id="46237-122">Aşağıdaki bölümlerde, her tür denetimi açıklar ve projelerinizde kullanılacak türü seçme önerileri verin.</span><span class="sxs-lookup"><span data-stu-id="46237-122">The following sections describe each kind of control and give recommendations for choosing the kind to use in your projects.</span></span>  
  
### <a name="composite-controls"></a><span data-ttu-id="46237-123">Bileşik denetimler</span><span class="sxs-lookup"><span data-stu-id="46237-123">Composite Controls</span></span>  
 <span data-ttu-id="46237-124">Bileşik Denetim, ortak bir kapsayıcıda kapsüllenmiş Windows Forms denetimleri koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="46237-124">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="46237-125">Bu tür bir denetim adlandırılan bir *kullanıcı denetimi*.</span><span class="sxs-lookup"><span data-stu-id="46237-125">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="46237-126">Kapsanan denetimleri adlı *bağlı denetimler*.</span><span class="sxs-lookup"><span data-stu-id="46237-126">The contained controls are called *constituent controls*.</span></span>  
  
 <span data-ttu-id="46237-127">Bileşik Denetim tüm her kapsanan Windows Forms denetimleri ile ilişkili devralınmış işlevselliğini içerir ve seçmeli olarak kullanıma sunar ve bunların özelliklerini bağlamak sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-127">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="46237-128">Bileşik Denetim işlevselliği çaba hiçbir ek geliştirme çabayla işleme varsayılan klavye büyük bir bölümünü de sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-128">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>  
  
 <span data-ttu-id="46237-129">Örneğin, bir veritabanı müşteri adresi verileri görüntülemek için bileşik denetim oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="46237-129">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="46237-130">Bu denetim içerebilir bir <xref:System.Windows.Forms.DataGridView> denetiminin veritabanı alanları görüntülemek için bir <xref:System.Windows.Forms.BindingSource> bir veri kaynağına bağlama işlemek için ve bir <xref:System.Windows.Forms.BindingNavigator> kayıtlarda taşımak için denetim.</span><span class="sxs-lookup"><span data-stu-id="46237-130">This control could include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="46237-131">Veri bağlama özellikleri seçerek maruz bırakabileceğinden ve paketini ve tüm denetim uygulama başka bir uygulama yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-131">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span> <span data-ttu-id="46237-132">Bu tür bir bileşik denetim örneği için bkz: [nasıl yapılır: Windows Forms denetimlerindeki öznitelikler uygulamak](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="46237-132">For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="46237-133">Bileşik Denetim yazmak için türetilen <xref:System.Windows.Forms.UserControl> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="46237-133">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="46237-134"><xref:System.Windows.Forms.UserControl> Temel sınıf sağlar klavye yönlendirme alt denetimleri ve bir grup olarak çalışmak alt denetimleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-134">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span> <span data-ttu-id="46237-135">Daha fazla bilgi için bkz: [bileşik Windows Forms denetimi geliştirme](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="46237-135">For more information, see [Developing a Composite Windows Forms Control](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="46237-136">**Öneri**</span><span class="sxs-lookup"><span data-stu-id="46237-136">**Recommendation**</span></span>  
  
 <span data-ttu-id="46237-137">Devralınan <xref:System.Windows.Forms.UserControl> varsa sınıfı:</span><span class="sxs-lookup"><span data-stu-id="46237-137">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>  
  
-   <span data-ttu-id="46237-138">Çeşitli Windows Forms denetimleri işlevlerini tek bir yeniden kullanılabilir birime birleştirmek istediğiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-138">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>  
  
### <a name="extended-controls"></a><span data-ttu-id="46237-139">Genişletilmiş denetimler</span><span class="sxs-lookup"><span data-stu-id="46237-139">Extended Controls</span></span>  
 <span data-ttu-id="46237-140">Varolan bir Windows Forms denetimden devralınan bir denetim türetilemeyeceğini.</span><span class="sxs-lookup"><span data-stu-id="46237-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="46237-141">Bu yaklaşımda, bir Windows Forms denetiminin devralınmış işlevselliğin korumak ve ardından özel özellikler, yöntemleri veya diğer özellikler ekleyerek bu işlevselliği genişletme.</span><span class="sxs-lookup"><span data-stu-id="46237-141">With this approach, you can retain all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="46237-142">Bu seçenekle temel denetimin boyama mantığı geçersiz kılmak ve ardından görünümünü değiştirerek kullanıcı arabirimiyle genişletmek.</span><span class="sxs-lookup"><span data-stu-id="46237-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>  
  
 <span data-ttu-id="46237-143">Örneğin, türetilmiş bir denetim oluşturabilirsiniz <xref:System.Windows.Forms.Button> bir kullanıcının kaç kez izleyen denetim tıkladığını onu.</span><span class="sxs-lookup"><span data-stu-id="46237-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>  
  
 <span data-ttu-id="46237-144">Bazı denetimler de bir özel görünüm denetiminizi grafik kullanıcı arabirimi için geçersiz kılarak ekleyebilirsiniz <xref:System.Windows.Forms.Control.OnPaint%2A> yöntemi temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="46237-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="46237-145">Tıklama izleyen bir genişletilmiş düğmesi için geçersiz kılabilirsiniz <xref:System.Windows.Forms.Control.OnPaint%2A> yöntemi, temel uygulamayı çağırması <xref:System.Windows.Forms.Control.OnPaint%2A>ve ardından bir köşesinde tıklatın sayısı çizin <xref:System.Windows.Forms.Button> denetimin istemci alanı.</span><span class="sxs-lookup"><span data-stu-id="46237-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>  
  
 <span data-ttu-id="46237-146">**Öneri**</span><span class="sxs-lookup"><span data-stu-id="46237-146">**Recommendation**</span></span>  
  
 <span data-ttu-id="46237-147">Windows Forms denetimden devralır:</span><span class="sxs-lookup"><span data-stu-id="46237-147">Inherit from a Windows Forms control if:</span></span>  
  
-   <span data-ttu-id="46237-148">Gereksinim duyduğunuz işlevselliği çoğunu zaten varolan bir Windows Forms denetimi aynı.</span><span class="sxs-lookup"><span data-stu-id="46237-148">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>  
  
-   <span data-ttu-id="46237-149">Bir özel grafik kullanıcı arabirimi gerekmez veya varolan bir denetim için yeni bir grafik kullanıcı arabirimini tasarlamak istersiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-149">You do not need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span>  
  
### <a name="custom-controls"></a><span data-ttu-id="46237-150">Özel denetimler</span><span class="sxs-lookup"><span data-stu-id="46237-150">Custom Controls</span></span>  
 <span data-ttu-id="46237-151">Bir denetim oluşturmak için başka bir önemli ölçüde başlangıçtan itibaren devralarak oluşturmak için yoludur <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="46237-151">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="46237-152"><xref:System.Windows.Forms.Control> Sınıfı tüm fare ve klavye olayları, işleme dahil olmak üzere denetimleri tarafından gereken temel işlevleri, ancak hiçbir denetim özgü işlevsellik ya da grafik arabirim sağlar.</span><span class="sxs-lookup"><span data-stu-id="46237-152">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>  
  
 <span data-ttu-id="46237-153">Bir denetimi devralarak oluşturma <xref:System.Windows.Forms.Control> sınıfı gerektiren çok daha fazla düşünce ve çaba içinden devralma daha <xref:System.Windows.Forms.UserControl> veya varolan bir Windows Forms denetimi.</span><span class="sxs-lookup"><span data-stu-id="46237-153">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="46237-154">Sizin için önemli uygulama sol çünkü denetiminizi bileşik veya genişletilmiş denetim çok esneklik olabilir ve tam ihtiyaçlarınıza en uygun denetim uyarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-154">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>  
  
 <span data-ttu-id="46237-155">Özel bir denetim uygulamak için kod yazma <xref:System.Windows.Forms.Control.OnPaint%2A> gereksinim duyduğunuz herhangi bir özelliğe özgü kod yanı sıra denetim olayı.</span><span class="sxs-lookup"><span data-stu-id="46237-155">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="46237-156">Ayrıca geçersiz kılabilirsiniz <xref:System.Windows.Forms.Control.WndProc%2A> doğrudan yöntemi ve tanıtıcı windows iletileri.</span><span class="sxs-lookup"><span data-stu-id="46237-156">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="46237-157">Bu en güçlü bir yöntemdir bir denetim oluşturmak için ancak bu tekniği etkili bir şekilde kullanmak için Microsoft Win32® API ile ilgili bilgi sahibi olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="46237-157">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>  
  
 <span data-ttu-id="46237-158">Özel bir denetimin görünümünü ve davranışını bir analog saatinin çoğaltan bir saat denetimi örneğidir.</span><span class="sxs-lookup"><span data-stu-id="46237-158">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="46237-159">Özel boyama yanıt olarak taşımak için saatin ellerini neden çağrıldığında <xref:System.Windows.Forms.Timer.Tick> iç olayları <xref:System.Windows.Forms.Timer> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="46237-159">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="46237-160">Daha fazla bilgi için bkz: [nasıl yapılır: basit bir Windows Forms denetimi geliştirme](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="46237-160">For more information, see [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="46237-161">**Öneri**</span><span class="sxs-lookup"><span data-stu-id="46237-161">**Recommendation**</span></span>  
  
 <span data-ttu-id="46237-162">Devralınan <xref:System.Windows.Forms.Control> varsa sınıfı:</span><span class="sxs-lookup"><span data-stu-id="46237-162">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>  
  
-   <span data-ttu-id="46237-163">Özel bir grafik gösterimi denetiminizin sağlamak istediğinizde.</span><span class="sxs-lookup"><span data-stu-id="46237-163">You want to provide a custom graphical representation of your control.</span></span>  
  
-   <span data-ttu-id="46237-164">Standart denetimler kullanılabilir olmayan özel işlevsellik uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="46237-164">You need to implement custom functionality that is not available through standard controls.</span></span>  
  
### <a name="activex-controls"></a><span data-ttu-id="46237-165">ActiveX Denetimleri</span><span class="sxs-lookup"><span data-stu-id="46237-165">ActiveX Controls</span></span>  
 <span data-ttu-id="46237-166">Windows Forms altyapı ana bilgisayar Windows Forms denetimleri için optimize edilmiştir rağmen ActiveX denetimlerini kullanmaya devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-166">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="46237-167">Visual Studio'da bu görev için desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="46237-167">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="46237-168">Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms ActiveX denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="46237-168">For more information, see [How to: Add ActiveX Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md).</span></span>  
  
### <a name="windowless-controls"></a><span data-ttu-id="46237-169">Penceresiz denetimleri</span><span class="sxs-lookup"><span data-stu-id="46237-169">Windowless Controls</span></span>  
 <span data-ttu-id="46237-170">The Microsoft Visual Basic® 6.0and ActiveX teknolojilerini destekleyen *penceresiz* kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="46237-170">The Microsoft Visual Basic® 6.0and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="46237-171">Windows Forms'ta penceresiz denetimleri desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="46237-171">Windowless controls are not supported in Windows Forms.</span></span>  
  
## <a name="custom-design-experience"></a><span data-ttu-id="46237-172">Özel tasarım deneyimi</span><span class="sxs-lookup"><span data-stu-id="46237-172">Custom Design Experience</span></span>  
 <span data-ttu-id="46237-173">Özel bir tasarım zamanı deneyimi uygulamanız gerekiyorsa, kendi Tasarımcısı yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46237-173">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="46237-174">Bileşik denetimler için özel Tasarımcı sınıfından türetilen <xref:System.Windows.Forms.Design.ParentControlDesigner> veya <xref:System.Windows.Forms.Design.DocumentDesigner> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="46237-174">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="46237-175">Genişletilmiş ve özel denetimler için özel Tasarımcı sınıfından türetilen <xref:System.Windows.Forms.Design.ControlDesigner> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="46237-175">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>  
  
 <span data-ttu-id="46237-176">Kullanım <xref:System.ComponentModel.DesignerAttribute> denetiminizi Tasarımcısı ile ilişkilendirilecek.</span><span class="sxs-lookup"><span data-stu-id="46237-176">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span> <span data-ttu-id="46237-177">Daha fazla bilgi için bkz: [genişletme tasarım zamanı desteği](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2) ve [nasıl yapılır: bir Windows Forms denetimi, geçen avantajı, tasarım-zamanı özellikleri oluşturma](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).</span><span class="sxs-lookup"><span data-stu-id="46237-177">For more information, see [Extending Design-Time Support](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2) and [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46237-178">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="46237-178">See Also</span></span>  
 [<span data-ttu-id="46237-179">Özel Windows Forms denetimleri .NET Framework ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="46237-179">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="46237-180">Nasıl yapılır: basit bir Windows Forms denetimi geliştirme</span><span class="sxs-lookup"><span data-stu-id="46237-180">How to: Develop a Simple Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [<span data-ttu-id="46237-181">Bileşik Windows Forms denetimi geliştirme</span><span class="sxs-lookup"><span data-stu-id="46237-181">Developing a Composite Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [<span data-ttu-id="46237-182">Tasarım zamanı desteği genişletme</span><span class="sxs-lookup"><span data-stu-id="46237-182">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="46237-183">Nasıl yapılır: tasarım-zamanı özellikleri yararlanan bir Windows Forms denetimi oluşturma</span><span class="sxs-lookup"><span data-stu-id="46237-183">How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features</span></span>](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)