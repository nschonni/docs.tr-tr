---
title: "Nasıl yapılır: İlk Fırsat Özel Durum Bildirimleri Alma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e61c037e85abfb362580930bbfeb7b06ba091f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-receive-first-chance-exception-notifications"></a><span data-ttu-id="de166-102">Nasıl yapılır: İlk Fırsat Özel Durum Bildirimleri Alma</span><span class="sxs-lookup"><span data-stu-id="de166-102">How to: Receive First-Chance Exception Notifications</span></span>
<span data-ttu-id="de166-103"><xref:System.AppDomain.FirstChanceException> Olayı <xref:System.AppDomain> sınıfı bir özel durum bildirimi olanak sağlar, önce ortak dil çalışma zamanı özel durum işleyicileri için arama başladı.</span><span class="sxs-lookup"><span data-stu-id="de166-103">The <xref:System.AppDomain.FirstChanceException> event of the <xref:System.AppDomain> class lets you receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 <span data-ttu-id="de166-104">Olay uygulama etki alanı düzeyinde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="de166-104">The event is raised at the application domain level.</span></span> <span data-ttu-id="de166-105">Bir uygulama etki alanında işlenmeyen bir özel durum başka bir uygulama etki alanında ele alınması için bir iş parçacığı yürütme birden çok uygulama etki alanları arasında geçiş yapabilir.</span><span class="sxs-lookup"><span data-stu-id="de166-105">A thread of execution can pass through multiple application domains, so an exception that is unhandled in one application domain could be handled in another application domain.</span></span> <span data-ttu-id="de166-106">Uygulama etki alanı özel durumu işler kadar olay işleyicisi eklenen her uygulama etki alanındaki bildirim oluşur.</span><span class="sxs-lookup"><span data-stu-id="de166-106">The notification occurs in each application domain that has added a handler for the event, until an application domain handles the exception.</span></span>  
  
 <span data-ttu-id="de166-107">Bu makaledeki örnekler ve yordamları bir uygulama etki alanına sahip basit bir program ve oluşturduğunuz uygulama etki alanı ilk fırsat özel durum bildirimleri almak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="de166-107">The procedures and examples in this article show how to receive first-chance exception notifications in a simple program that has one application domain, and in an application domain that you create.</span></span>  
  
 <span data-ttu-id="de166-108">Örneğin, birkaç uygulama etki alanları kapsayan daha karmaşık bir örnek için bkz <xref:System.AppDomain.FirstChanceException> olay.</span><span class="sxs-lookup"><span data-stu-id="de166-108">For a more complex example that spans several application domains, see the example for the <xref:System.AppDomain.FirstChanceException> event.</span></span>  
  
## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="de166-109">Varsayılan uygulama etki alanında ilk fırsat özel durum bildirimleri alma</span><span class="sxs-lookup"><span data-stu-id="de166-109">Receiving First-Chance Exception Notifications in the Default Application Domain</span></span>  
 <span data-ttu-id="de166-110">Aşağıdaki yordamda, bir uygulama için giriş noktası `Main()` yöntemi, varsayılan uygulama etki alanında çalışır.</span><span class="sxs-lookup"><span data-stu-id="de166-110">In the following procedure, the entry point for the application, the `Main()` method, runs in the default application domain.</span></span>  
  
#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="de166-111">Varsayılan uygulama etki alanında ilk fırsat özel durum bildirimleri göstermek için</span><span class="sxs-lookup"><span data-stu-id="de166-111">To demonstrate first-chance exception notifications in the default application domain</span></span>  
  
1.  <span data-ttu-id="de166-112">Bir olay işleyicisi tanımlama <xref:System.AppDomain.FirstChanceException> olay, bir lambda kullanarak işlev ve olaya ekleme.</span><span class="sxs-lookup"><span data-stu-id="de166-112">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event, using a lambda function, and attach it to the event.</span></span> <span data-ttu-id="de166-113">Bu örnekte, olay işleyicisi nerede olay işlenmiş uygulama etki alanı adı ve özel durumun yazdırır <xref:System.Exception.Message%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="de166-113">In this example, the event handler prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  <span data-ttu-id="de166-114">Bir özel durum ve onu yakalayın.</span><span class="sxs-lookup"><span data-stu-id="de166-114">Throw an exception and catch it.</span></span> <span data-ttu-id="de166-115">Çalışma zamanı özel durum işleyici bulur önce <xref:System.AppDomain.FirstChanceException> olay tetiklenir ve bir ileti görüntüler.</span><span class="sxs-lookup"><span data-stu-id="de166-115">Before the runtime locates the exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="de166-116">Bu ileti özel durum işleyicisi tarafından görüntülenen ileti tarafından izlenir.</span><span class="sxs-lookup"><span data-stu-id="de166-116">This message is followed by the message that is displayed by the exception handler.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  <span data-ttu-id="de166-117">Bir özel durum, ancak bunu catch değil.</span><span class="sxs-lookup"><span data-stu-id="de166-117">Throw an exception, but do not catch it.</span></span> <span data-ttu-id="de166-118">Bir özel durum işleyicisi için çalışma zamanı görünür önce <xref:System.AppDomain.FirstChanceException> olay tetiklenir ve bir ileti görüntüler.</span><span class="sxs-lookup"><span data-stu-id="de166-118">Before the runtime looks for an exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="de166-119">Uygulama sonlanana için hiçbir özel durum işleyici yok.</span><span class="sxs-lookup"><span data-stu-id="de166-119">There is no exception handler, so the application terminates.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     <span data-ttu-id="de166-120">Bu yordamın ilk üç adımda gösterilen kodu tam konsol uygulaması oluşturur.</span><span class="sxs-lookup"><span data-stu-id="de166-120">The code that is shown in the first three steps of this procedure forms a complete console application.</span></span> <span data-ttu-id="de166-121">Varsayılan uygulama etki alanı adı .exe dosya uzantısını ve adını oluştuğundan uygulamadan çıktı, .exe dosya adı bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="de166-121">The output from the application varies, depending on the name of the .exe file, because the name of the default application domain consists of the name and extension of the .exe file.</span></span> <span data-ttu-id="de166-122">Aşağıdaki örnek çıktı için bakın.</span><span class="sxs-lookup"><span data-stu-id="de166-122">See the following for sample output.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a><span data-ttu-id="de166-123">Başka bir uygulama etki alanında ilk fırsat özel durum bildirimleri alma</span><span class="sxs-lookup"><span data-stu-id="de166-123">Receiving First-Chance Exception Notifications in Another Application Domain</span></span>  
 <span data-ttu-id="de166-124">Programınızı birden fazla uygulama etki alanı varsa, hangi uygulama etki alanları bildirimlerin seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="de166-124">If your program contains more than one application domain, you can choose which application domains receive notifications.</span></span>  
  
#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a><span data-ttu-id="de166-125">Oluşturduğunuz bir uygulama etki alanında ilk fırsat özel durum bildirimleri almak için</span><span class="sxs-lookup"><span data-stu-id="de166-125">To receive first-chance exception notifications in an application domain that you create</span></span>  
  
1.  <span data-ttu-id="de166-126">Bir olay işleyicisi tanımlama <xref:System.AppDomain.FirstChanceException> olay.</span><span class="sxs-lookup"><span data-stu-id="de166-126">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="de166-127">Bu örnekte bir `static` yöntemi (`Shared` yöntemi Visual Basic'te) nerede olay işlenmiş uygulama etki alanı adı ve özel durumun yazdırır <xref:System.Exception.Message%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="de166-127">This example uses a `static` method (`Shared` method in Visual Basic) that prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  <span data-ttu-id="de166-128">Uygulama etki alanı oluşturma ve olay işleyicisi ekleme <xref:System.AppDomain.FirstChanceException> olay o uygulama etki alanı.</span><span class="sxs-lookup"><span data-stu-id="de166-128">Create an application domain and add the event handler to the <xref:System.AppDomain.FirstChanceException> event for that application domain.</span></span> <span data-ttu-id="de166-129">Bu örnekte, uygulama etki alanı adında `AD1`.</span><span class="sxs-lookup"><span data-stu-id="de166-129">In this example, the application domain is named `AD1`.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     <span data-ttu-id="de166-130">Varsayılan uygulama etki alanında bu olay aynı şekilde işleyebilir.</span><span class="sxs-lookup"><span data-stu-id="de166-130">You can handle this event in the default application domain in the same way.</span></span> <span data-ttu-id="de166-131">Kullanım `static` (`Shared` Visual Basic'te) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> özelliğinde `Main()` varsayılan uygulama etki alanı için bir başvuru alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="de166-131">Use the `static` (`Shared` in Visual Basic) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property in `Main()` to get a reference to the default application domain.</span></span>  
  
#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a><span data-ttu-id="de166-132">Uygulama etki alanında ilk fırsat özel durum bildirimleri göstermek için</span><span class="sxs-lookup"><span data-stu-id="de166-132">To demonstrate first-chance exception notifications in the application domain</span></span>  
  
1.  <span data-ttu-id="de166-133">Oluşturma bir `Worker` önceki yordamda oluşturduğunuz uygulama etki alanı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="de166-133">Create a `Worker` object in the application domain that you created in the previous procedure.</span></span> <span data-ttu-id="de166-134">`Worker` Sınıfı genel olmalıdır ve öğesinden türetilmelidir <xref:System.MarshalByRefObject>, bu makalenin sonunda eksiksiz örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="de166-134">The `Worker` class must be public, and must derive from <xref:System.MarshalByRefObject>, as shown in the complete example at the end of this article.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  <span data-ttu-id="de166-135">Bir yöntemi çağırmak `Worker` aykırı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="de166-135">Call a method of the `Worker` object that throws an exception.</span></span> <span data-ttu-id="de166-136">Bu örnekte, `Thrower` yöntemi iki kez çağrılır.</span><span class="sxs-lookup"><span data-stu-id="de166-136">In this example, the `Thrower` method is called twice.</span></span> <span data-ttu-id="de166-137">İlk kez yöntemi değişkendir `true`, kendi özel durumu yakalamak yöntem neden olur.</span><span class="sxs-lookup"><span data-stu-id="de166-137">The first time, the method argument is `true`, which causes the method to catch its own exception.</span></span> <span data-ttu-id="de166-138">Bağımsız değişken ikincisinde ise, değer `false`ve `Main()` yöntemi özel durum varsayılan uygulama etki alanındaki yakalar.</span><span class="sxs-lookup"><span data-stu-id="de166-138">The second time, the argument is `false`, and the `Main()` method catches the exception in the default application domain.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  <span data-ttu-id="de166-139">Yerleştirin kodda `Thrower` yöntemi kendi özel durumu işler olup olmadığını denetlemek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="de166-139">Place code in the `Thrower` method to control whether the method handles its own exception.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="de166-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="de166-140">Example</span></span>  
 <span data-ttu-id="de166-141">Aşağıdaki örnek adlı bir uygulama etki alanı oluşturur `AD1` ve uygulama etki alanına ait bir olay işleyicisi ekler <xref:System.AppDomain.FirstChanceException> olay.</span><span class="sxs-lookup"><span data-stu-id="de166-141">The following example creates an application domain named `AD1` and adds an event handler to the application domain's <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="de166-142">Örnek bir örneğini oluşturur `Worker` sınıfı uygulama etki alanı ve bir yöntem adlı çağrıları `Thrower` oluşturur, bir <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="de166-142">The example creates an instance of the `Worker` class in the application domain, and calls a method named `Thrower` that throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="de166-143">Bağımsız değişken değeri, bağlı olarak yöntemi özel durum yakalar ya da işlenmesi başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="de166-143">Depending on the value of its argument, the method either catches the exception or fails to handle it.</span></span>  
  
 <span data-ttu-id="de166-144">Her zaman `Thrower` yöntemi bir özel durum oluşturur `AD1`, <xref:System.AppDomain.FirstChanceException> olayı oluşturulur `AD1`, ve olay işleyicisi bir ileti görüntüler.</span><span class="sxs-lookup"><span data-stu-id="de166-144">Each time the `Thrower` method throws an exception in `AD1`, the <xref:System.AppDomain.FirstChanceException> event is raised in `AD1`, and the event handler displays a message.</span></span> <span data-ttu-id="de166-145">Çalışma zamanı sonra bir özel durum işleyici arar.</span><span class="sxs-lookup"><span data-stu-id="de166-145">The runtime then looks for an exception handler.</span></span> <span data-ttu-id="de166-146">İlk durumda, özel durum işleyici içinde bulunur `AD1`.</span><span class="sxs-lookup"><span data-stu-id="de166-146">In the first case, the exception handler is found in `AD1`.</span></span> <span data-ttu-id="de166-147">İkinci durumda, özel durum işlenmemiş `AD1`ve bunun yerine varsayılan uygulama etki alanında yakalandı.</span><span class="sxs-lookup"><span data-stu-id="de166-147">In the second case, the exception is unhandled in `AD1`, and instead is caught in the default application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de166-148">Varsayılan uygulama etki alanı adı yürütülebilir dosyanın adını ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="de166-148">The name of the default application domain is the same as the name of the executable.</span></span>  
  
 <span data-ttu-id="de166-149">İçin bir işleyici eklediğinizde <xref:System.AppDomain.FirstChanceException> varsayılan uygulama etki alanı, olay için olay gerçekleşti ve varsayılan uygulama etki alanı özel durumu işler önce işlenir.</span><span class="sxs-lookup"><span data-stu-id="de166-149">If you add a handler for the <xref:System.AppDomain.FirstChanceException> event to the default application domain, the event is raised and handled before the default application domain handles the exception.</span></span> <span data-ttu-id="de166-150">Bu görmek için C# kod ekleme `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (Visual Basic'te `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) başında `Main()`.</span><span class="sxs-lookup"><span data-stu-id="de166-150">To see this, add the C# code `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (in Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) at the beginning of `Main()`.</span></span>  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de166-151">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="de166-151">Compiling the Code</span></span>  
  
-   <span data-ttu-id="de166-152">Bu örnek, bir komut satırı uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="de166-152">This example is a command-line application.</span></span> <span data-ttu-id="de166-153">Derlemek ve bu kodu çalıştırmak için [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], C# kod ekleme `Console.ReadLine();` (Visual Basic'te `Console.ReadLine()`) sonunda `Main()`, çıktı okuyabilmesi kapatma komut penceresinde önlemek için.</span><span class="sxs-lookup"><span data-stu-id="de166-153">To compile and run this code in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], add the C# code `Console.ReadLine();` (in Visual Basic, `Console.ReadLine()`) at the end of `Main()`, to prevent the command window from closing before you can read the output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de166-154">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="de166-154">See Also</span></span>  
 <xref:System.AppDomain.FirstChanceException>