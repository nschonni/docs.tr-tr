---
title: "Olay (Visual Basic) bildirme ve oluşturma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bf75cfba5102be5d837af385e2d3578f78a03c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="383ac-102">İzlenecek yol: Olay Bildirme ve Oluşturma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="383ac-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="383ac-103">Bu kılavuz, bildirme ve olayları adlı bir sınıf için yükseltmek gösterilmiştir `Widget`.</span><span class="sxs-lookup"><span data-stu-id="383ac-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="383ac-104">Adımları tamamladıktan sonra Yardımcısı konuyu okumak isteyebilirsiniz [izlenecek yol: olayları işleme](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), olayları kullanmayı gösterir `Widget` bir uygulamada durum bilgilerini sağlamak için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="383ac-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="383ac-105">Pencere sınıfı</span><span class="sxs-lookup"><span data-stu-id="383ac-105">The Widget Class</span></span>  
 <span data-ttu-id="383ac-106">Sahip olduğunuz şu anda varsayın bir `Widget` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="383ac-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="383ac-107">`Widget` Tamamlama göstergesi çeşit yerleştirmek, uygulamanızın istediğiniz ve sınıfı yürütmek için uzun zaman alabilir bir yöntem vardır.</span><span class="sxs-lookup"><span data-stu-id="383ac-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="383ac-108">Elbette, yapabilir `Widget` nesne tamamlanma yüzdesi iletişim kutusunu göster, ancak daha sonra bu iletişim kutusu, kullandığınız her projede takılmış `Widget` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="383ac-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="383ac-109">Bir nesne tanıtıcısının kullanıcı arabirimi kullanan uygulama izin vermek için nesne tasarımı iyi ilkesi olan — bir form veya iletişim kutusu yönetmek için tüm nesne amacı olmadığı sürece.</span><span class="sxs-lookup"><span data-stu-id="383ac-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="383ac-110">Amacı `Widget` eklemek daha iyi şekilde diğer görevleri gerçekleştirmek için bir `PercentDone` olay ve let çağıran yordamı `Widget`kullanıcının yöntemlerini işlemek olay ve görüntü durumunu güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="383ac-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="383ac-111">`PercentDone` Olay ayrıca görev iptal etmek için bir mekanizma sağlar.</span><span class="sxs-lookup"><span data-stu-id="383ac-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="383ac-112">Bu konu için kod örneği oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="383ac-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="383ac-113">Yeni bir [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows uygulaması proje ve adlı bir form oluşturun `Form1`.</span><span class="sxs-lookup"><span data-stu-id="383ac-113">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="383ac-114">İki düğme ve bir etiket eklemek `Form1`.</span><span class="sxs-lookup"><span data-stu-id="383ac-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="383ac-115">Aşağıdaki tabloda gösterildiği gibi nesneleri adlandırın.</span><span class="sxs-lookup"><span data-stu-id="383ac-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="383ac-116">Nesne</span><span class="sxs-lookup"><span data-stu-id="383ac-116">Object</span></span>|<span data-ttu-id="383ac-117">Özellik</span><span class="sxs-lookup"><span data-stu-id="383ac-117">Property</span></span>|<span data-ttu-id="383ac-118">Ayar</span><span class="sxs-lookup"><span data-stu-id="383ac-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="383ac-119">Başlangıç görevi</span><span class="sxs-lookup"><span data-stu-id="383ac-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="383ac-120">İptal</span><span class="sxs-lookup"><span data-stu-id="383ac-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="383ac-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="383ac-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="383ac-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="383ac-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="383ac-123">Üzerinde **proje** menüsünde seçin **sınıfı Ekle** adlı bir sınıf eklemek için `Widget.vb` projeye.</span><span class="sxs-lookup"><span data-stu-id="383ac-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="383ac-124">Pencere sınıfı için bir olay bildirmek için</span><span class="sxs-lookup"><span data-stu-id="383ac-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="383ac-125">Kullanım `Event` olayda bildirmek için anahtar sözcüğü `Widget` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="383ac-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="383ac-126">Bir olay olabilir Not `ByVal` ve `ByRef` bağımsız değişken olarak `Widget`'s `PercentDone` olay gösterir:</span><span class="sxs-lookup"><span data-stu-id="383ac-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="383ac-127">Ne zaman çağıran nesne alır bir `PercentDone` olayı `Percent` bağımsız değişkeni tamamlandıktan görev yüzdesini içerir.</span><span class="sxs-lookup"><span data-stu-id="383ac-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="383ac-128">`Cancel` Bağımsız değişkeni ayarlanabilir `True` olayı yöntemi iptal etmek için.</span><span class="sxs-lookup"><span data-stu-id="383ac-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="383ac-129">Yordamlar, aşağıdaki istisnalar dışında bağımsız gibi olay bağımsız bildirebilir: olayları olamaz `Optional` veya `ParamArray` bağımsız değişkenleri ve olaylar, dönüş değerleri gerekmez.</span><span class="sxs-lookup"><span data-stu-id="383ac-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="383ac-130">`PercentDone` Olayı tarafından `LongTask` yöntemi `Widget` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="383ac-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="383ac-131">`LongTask`iki bağımsız değişkeni alır: süre yöntemi çalışma ve önce en az zaman aralığını yaparak amaçları olan kişilerle tanışabilirsiniz `LongTask` yükseltmek için duraklatır `PercentDone` olay.</span><span class="sxs-lookup"><span data-stu-id="383ac-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="383ac-132">PercentDone olay yükseltmek için</span><span class="sxs-lookup"><span data-stu-id="383ac-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="383ac-133">Erişimi kolaylaştırmak için `Timer` Bu sınıf tarafından kullanılan özellik ekleme bir `Imports` sınıfı modülünüzün bildirimler bölümünün üst ifadesine yukarıda `Class Widget` deyimi.</span><span class="sxs-lookup"><span data-stu-id="383ac-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="383ac-134">Aşağıdaki kodu ekleyin `Widget` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="383ac-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="383ac-135">Uygulamanızı çağırdığında `LongTask` yöntemi, `Widget` sınıfı başlatır `PercentDone` olay her `MinimumInterval` saniye.</span><span class="sxs-lookup"><span data-stu-id="383ac-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="383ac-136">Olay geri döndüğünde, `LongTask` denetler `Cancel` bağımsız değişkeni ayarlandığı `True`.</span><span class="sxs-lookup"><span data-stu-id="383ac-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="383ac-137">Bazı bildirimler burada gereklidir.</span><span class="sxs-lookup"><span data-stu-id="383ac-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="383ac-138">Basitleştirmek için `LongTask` yordam varsayar bildiğiniz önceden görevin ne kadar sürer.</span><span class="sxs-lookup"><span data-stu-id="383ac-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="383ac-139">Bu neredeyse hiçbir zaman bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="383ac-139">This is almost never the case.</span></span> <span data-ttu-id="383ac-140">Görevler bile boyutu parçalara bölmek zor olabilir ve genellikle de en önemli ne kullanıcılara yalnızca bir şey olmuyor göstergesidir elde önce geçen zamanı miktarıdır.</span><span class="sxs-lookup"><span data-stu-id="383ac-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="383ac-141">Bu örnekte başka bir kusur anlaþýlmaz.</span><span class="sxs-lookup"><span data-stu-id="383ac-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="383ac-142">`Timer` Özelliği gece yarısından beri geçen saniye sayısını döndürür; bu nedenle, yalnızca gece yarısından önce başlattıysanız uygulama takılmış.</span><span class="sxs-lookup"><span data-stu-id="383ac-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="383ac-143">Sürenin ölçülmesine daha dikkatli bir yaklaşım gibi bu sınır koşulları dikkate alın veya bunları tamamen özellikler gibi kullanmaktan kaçının `Now`.</span><span class="sxs-lookup"><span data-stu-id="383ac-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="383ac-144">Şimdi `Widget` sınıf olayları oluşturma, sonraki izlenecek taşıyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="383ac-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="383ac-145">[İzlenecek yol: Olaylarını işleme](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) nasıl kullanılacağı ortaya `WithEvents` olay işleyicisi ile ilişkilendirilecek `PercentDone` olay.</span><span class="sxs-lookup"><span data-stu-id="383ac-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383ac-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="383ac-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [<span data-ttu-id="383ac-147">İzlenecek yol: Olayları işleme</span><span class="sxs-lookup"><span data-stu-id="383ac-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [<span data-ttu-id="383ac-148">Olayları</span><span class="sxs-lookup"><span data-stu-id="383ac-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)