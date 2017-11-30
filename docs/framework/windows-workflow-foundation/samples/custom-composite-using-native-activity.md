---
title: "Özel bileşik yerel etkinliğini kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7af9562f38b68acc95c051e85d007ce9bd5a2c87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="custom-composite-using-native-activity"></a><span data-ttu-id="158d7-102">Özel bileşik yerel etkinliğini kullanma</span><span class="sxs-lookup"><span data-stu-id="158d7-102">Custom Composite using Native Activity</span></span>
<span data-ttu-id="158d7-103">Bu örnek nasıl yazılacağını göstermektedir bir <xref:System.Activities.NativeActivity> diğer zamanlar <xref:System.Activities.Activity> bir iş akışının yürütme akışını denetlemek için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="158d7-103">This sample demonstrates how to write a <xref:System.Activities.NativeActivity> that schedules other <xref:System.Activities.Activity> objects to control the flow of a workflow’s execution.</span></span> <span data-ttu-id="158d7-104">Bu örnek iki ortak denetim akışı, kullandığı sıra ve çalışırken, bunun nasıl yapılacağını göstermek için.</span><span class="sxs-lookup"><span data-stu-id="158d7-104">This sample uses two common control flows, Sequence and While, to demonstrate how to do this.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="158d7-105">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="158d7-105">Sample Details</span></span>  
 <span data-ttu-id="158d7-106">İle başlayarak `MySequence`, öğesinden türetilen fark edilecek ilk şey. <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="158d7-106">Starting with `MySequence`, the first thing to notice is that it derives from <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="158d7-107"><xref:System.Activities.NativeActivity>olan <xref:System.Activities.Activity> iş akışı çalışma zamanı tüm tekliflerden gösteren nesne <xref:System.Activities.NativeActivityContext> geçirilen `Execute` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="158d7-107"><xref:System.Activities.NativeActivity> is the <xref:System.Activities.Activity> object that exposes the full breadth of the workflow runtime through the <xref:System.Activities.NativeActivityContext> passed to the `Execute` method.</span></span>  
  
 <span data-ttu-id="158d7-108">`MySequence`ortak bir topluluğu gösterir <xref:System.Activities.Activity> iş akışı yazarı tarafından doldurulmuş nesneleri.</span><span class="sxs-lookup"><span data-stu-id="158d7-108">`MySequence` exposes a public collection of <xref:System.Activities.Activity> objects that gets populated by the workflow author.</span></span> <span data-ttu-id="158d7-109">İş akışı yürütülmeden önce iş akışı çalışma zamanı çağırır <xref:System.Activities.Activity.CacheMetadata%2A> bir iş akışındaki her etkinlik üzerinde yöntemi.</span><span class="sxs-lookup"><span data-stu-id="158d7-109">Before the workflow is executed, the workflow runtime calls the <xref:System.Activities.Activity.CacheMetadata%2A> method on each activity in a workflow.</span></span> <span data-ttu-id="158d7-110">Bu işlem sırasında çalışma zamanı verileri kapsamı ve ömür boyu yönetimi için üst-alt ilişki kurar.</span><span class="sxs-lookup"><span data-stu-id="158d7-110">During this process, the runtime establishes parent-child relationships for data scoping and lifetime management.</span></span> <span data-ttu-id="158d7-111">Varsayılan uygulaması <xref:System.Activities.Activity.CacheMetadata%2A> yöntemi kullanan <xref:System.ComponentModel.TypeDescriptor> örneği için sınıf `MySequence` herhangi bir ortak özellik türü eklemek için etkinlik <xref:System.Activities.Activity> veya <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Activity>> alt öğeleri olarak `MySequence` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="158d7-111">The default implementation of the <xref:System.Activities.Activity.CacheMetadata%2A> method uses the <xref:System.ComponentModel.TypeDescriptor> instance class for the `MySequence` activity to add any public property of type <xref:System.Activities.Activity> or <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>> as children of the `MySequence` activity.</span></span>  
  
 <span data-ttu-id="158d7-112">Aktivite ortak bir alt etkinlikler koleksiyonu gösterir olduğunda, bu alt etkinliklerin durumunu paylaşan olasıdır.</span><span class="sxs-lookup"><span data-stu-id="158d7-112">Whenever an activity exposes a public collection of child activities, it is likely those child activities share state.</span></span> <span data-ttu-id="158d7-113">Üst etkinlik için en iyi uygulama bu durumda olan `MySequence`, ayrıca bir koleksiyon üzerinden alt etkinlikleri gerçekleştirmek bu değişkenlerin kullanıma sunmak için.</span><span class="sxs-lookup"><span data-stu-id="158d7-113">It is a best practice for the parent activity, in this case `MySequence`, to also expose a collection of variables through which the child activities can accomplish this.</span></span> <span data-ttu-id="158d7-114">Alt etkinlikler gibi <xref:System.Activities.Activity.CacheMetadata%2A> yöntemi ekler türünün ortak özelliklerine <xref:System.Activities.Variable> veya <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Variable>> ile ilişkili değişkenleri olarak `MySequence` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="158d7-114">Like child activities, the <xref:System.Activities.Activity.CacheMetadata%2A> method adds public properties of type <xref:System.Activities.Variable> or <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>> as variables associated with the `MySequence` activity.</span></span>  
  
 <span data-ttu-id="158d7-115">Genel değişkenler yanı sıra hangi yönetilen alt tarafından `MySequence`, `MySequence` aynı zamanda, alt öğelerinin yürütmede olduğu izlenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="158d7-115">Besides the public variables, which are manipulated by the children of `MySequence`, `MySequence` must also keep track of where it is in the execution of its children.</span></span> <span data-ttu-id="158d7-116">Özel bir değişkene kullanan `currentIndex`, bunu başarmak için.</span><span class="sxs-lookup"><span data-stu-id="158d7-116">It uses a private variable, `currentIndex`, to accomplish this.</span></span> <span data-ttu-id="158d7-117">Bu değişken bir parçası olarak kayıtlı `MySequence` yapılan bir çağrı ekleyerek ortamı <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> yöntemi içinde `MySequence` etkinliğin <xref:System.Activities.Activity.CacheMetadata%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="158d7-117">This variable is registered as part of the `MySequence` environment by adding a call to the <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> method within the `MySequence` activity’s <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="158d7-118"><xref:System.Activities.Activity> Eklenen nesneleri `MySequence` `Activities` koleksiyon değişkenleri bu şekilde eklenen erişemiyor.</span><span class="sxs-lookup"><span data-stu-id="158d7-118">The <xref:System.Activities.Activity> objects added to the `MySequence` `Activities` collection cannot access variables added this way.</span></span>  
  
 <span data-ttu-id="158d7-119">Zaman `MySequence` çalışma zamanı tarafından çalışma zamanı çağrıları yürütülen kendi <xref:System.Activities.NativeActivity.Execute%2A> tümleştirilmesidir yöntemi, bir <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="158d7-119">When `MySequence` is executed by the runtime, the runtime calls its <xref:System.Activities.NativeActivity.Execute%2A> method, passing in an <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="158d7-120"><xref:System.Activities.NativeActivityContext> Etkinliğin proxy bağımsız değişkenleri ve değişkenleri başvurusunun kaldırılmasının yanı sıra diğer zamanlama için yeniden çalışma zamanı içine <xref:System.Activities.Activity> nesneleri veya `ActivityDelegates`.</span><span class="sxs-lookup"><span data-stu-id="158d7-120">The <xref:System.Activities.NativeActivityContext> is the activity’s proxy back into the runtime for dereferencing arguments and variables as well as scheduling other <xref:System.Activities.Activity> objects, or `ActivityDelegates`.</span></span> <span data-ttu-id="158d7-121">`MySequence`kullanan bir `InternalExecute` ilk alt ve tek bir yöntem sonraki tüm alt öğeleri zamanlama mantığını saklamak üzere yöntemi.</span><span class="sxs-lookup"><span data-stu-id="158d7-121">`MySequence` uses an `InternalExecute` method to encapsulate the logic of scheduling the first child and all subsequent children in a single method.</span></span> <span data-ttu-id="158d7-122">Başvurusunun kaldırılmasının tarafından başlatır `currentIndex`.</span><span class="sxs-lookup"><span data-stu-id="158d7-122">It starts by dereferencing the `currentIndex`.</span></span> <span data-ttu-id="158d7-123">Sayıma eşit ise `Activities` koleksiyonu sonra sırası tamamlandığında, etkinlik herhangi bir iş zamanlaması olmadan döndürür ve çalışma zamanı içine taşır <xref:System.Activities.ActivityInstanceState.Closed> durumu.</span><span class="sxs-lookup"><span data-stu-id="158d7-123">If it is equal to the count in the `Activities` collection, then the sequence is finished, the activity returns without scheduling any work and the runtime moves it into the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="158d7-124">Varsa `currentIndex` küçük etkinlikleri sayısından sonraki alt alanından elde edilen `Activities` koleksiyonu ve `MySequence` çağrıları <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, alt zamanlanması için geçen ve <xref:System.Activities.CompletionCallback> işaret adresindeki `InternalExecute` yöntem.</span><span class="sxs-lookup"><span data-stu-id="158d7-124">If the `currentIndex` is less than the count of activities, the next child is obtained from the `Activities` collection and `MySequence` calls <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, passing in the child to be scheduled and a <xref:System.Activities.CompletionCallback> that points at the `InternalExecute` method.</span></span> <span data-ttu-id="158d7-125">Son olarak, `currentIndex` artırılır ve denetim çalışma zamanına belirlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="158d7-125">Finally, the `currentIndex` is incremented and control is yielded back to the runtime.</span></span> <span data-ttu-id="158d7-126">En çok bir örneği olarak `MySequence` alt sahip <xref:System.Activities.Activity> zamanlanmış nesnesi, çalışma zamanı göz önünde bulundurur yürütülme durumunda olması için.</span><span class="sxs-lookup"><span data-stu-id="158d7-126">As long as an instance of `MySequence` has a child <xref:System.Activities.Activity> object scheduled, the runtime considers it to be in the Executing state.</span></span>  
  
 <span data-ttu-id="158d7-127">Alt etkinlik tamamlandığında <xref:System.Activities.CompletionCallback> yürütülür.</span><span class="sxs-lookup"><span data-stu-id="158d7-127">When the child activity completes, the <xref:System.Activities.CompletionCallback> is executed.</span></span> <span data-ttu-id="158d7-128">Döngü üstten devam eder.</span><span class="sxs-lookup"><span data-stu-id="158d7-128">The loop continues from the top.</span></span> <span data-ttu-id="158d7-129">Gibi `Execute`, <xref:System.Activities.CompletionCallback> geçen bir <xref:System.Activities.NativeActivityContext>, çalışma zamanı uygulayan erişim veren.</span><span class="sxs-lookup"><span data-stu-id="158d7-129">Like `Execute`, a <xref:System.Activities.CompletionCallback> takes an <xref:System.Activities.NativeActivityContext>, giving the implementer access to the runtime.</span></span>  
  
 <span data-ttu-id="158d7-130">`MyWhile`farklı `MySequence` tek bir zamanlar, <xref:System.Activities.Activity> art arda nesne ve kullanan bir <xref:System.Activities.Activity%601>< bool\> adlı `Condition` Bu zamanlama gerçekleşip gerçekleşmediğini belirlemek için.</span><span class="sxs-lookup"><span data-stu-id="158d7-130">`MyWhile` differs from `MySequence` in that it schedules a single <xref:System.Activities.Activity> object repeatedly, and in that it uses a <xref:System.Activities.Activity%601><bool\> named `Condition` to determine whether this scheduling should occur.</span></span> <span data-ttu-id="158d7-131">Gibi `MySequence`, `MyWhile` kullanan bir `InternalExecute` yöntemi, zamanlama mantığını merkezileştirme.</span><span class="sxs-lookup"><span data-stu-id="158d7-131">Like `MySequence`, `MyWhile` uses an `InternalExecute` method to centralize its scheduling logic.</span></span> <span data-ttu-id="158d7-132">Bu zamanlamaları `Condition` <xref:System.Activities.Activity>< bool\> ile bir <xref:System.Activities.CompletionCallback%601> \<bool > adlı `OnEvaluationCompleted`.</span><span class="sxs-lookup"><span data-stu-id="158d7-132">It schedules the `Condition`<xref:System.Activities.Activity><bool\> with a <xref:System.Activities.CompletionCallback%601>\<bool> named `OnEvaluationCompleted`.</span></span> <span data-ttu-id="158d7-133">Zaman yürütülmesi `Condition` olan tamamlandı, sonuç bu kullanılabilir duruma <xref:System.Activities.CompletionCallback> adlı kesin türü belirtilmiş bir parametreye `result`.</span><span class="sxs-lookup"><span data-stu-id="158d7-133">When the execution of `Condition` is completed, its result becomes available through this <xref:System.Activities.CompletionCallback> in a strongly-typed parameter named `result`.</span></span> <span data-ttu-id="158d7-134">Varsa `true`, `MyWhile` çağrıları <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, içinde geçen `Body` <xref:System.Activities.Activity> nesne ve `InternalExecute` olarak <xref:System.Activities.CompletionCallback>.</span><span class="sxs-lookup"><span data-stu-id="158d7-134">If `true`, `MyWhile` calls  <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, passing in the `Body`<xref:System.Activities.Activity> object and `InternalExecute` as the <xref:System.Activities.CompletionCallback>.</span></span> <span data-ttu-id="158d7-135">Zaman yürütülmesi `Body` tamamlandıktan `Condition` yeniden zamanlanmış `InternalExecute`, döngü üzerinden yeniden başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="158d7-135">When the execution of `Body` completes, `Condition` gets scheduled again in `InternalExecute`, starting the loop over again.</span></span> <span data-ttu-id="158d7-136">Zaman `Condition` döndürür `false`, örneği `MyWhile` verir denetim geri çalışma zamanına zamanlama olmadan `Body` ve çalışma zamanı taşınır <xref:System.Activities.ActivityInstanceState.Closed> durumu.</span><span class="sxs-lookup"><span data-stu-id="158d7-136">When the `Condition` returns `false`, an instance of `MyWhile` gives control back to the runtime without scheduling the `Body` and the runtime moves it to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="158d7-137">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="158d7-137">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="158d7-138">Composite.sln örnek çözümü açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158d7-138">Open the Composite.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="158d7-139">Derleme ve çözümü çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="158d7-139">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="158d7-140">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="158d7-140">The samples may already be installed on your machine.</span></span> <span data-ttu-id="158d7-141">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="158d7-141">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="158d7-142">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="158d7-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="158d7-143">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="158d7-143">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`  
  
## <a name="see-also"></a><span data-ttu-id="158d7-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="158d7-144">See Also</span></span>