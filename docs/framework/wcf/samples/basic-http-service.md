---
title: Temel HTTP Hizmeti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf4d40bce37dea65f2a27421de736779e467e728
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="basic-http-service"></a><span data-ttu-id="6851f-102">Temel HTTP Hizmeti</span><span class="sxs-lookup"><span data-stu-id="6851f-102">Basic HTTP Service</span></span>
<span data-ttu-id="6851f-103">Bu örnek, özellik "POX" (düz eski XML) hizmet vermek için başvurulan – kullanarak bir HTTP tabanlı, RPC tabanlı hizmeti - uygulama gösterilmiştir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST programlama modeli.</span><span class="sxs-lookup"><span data-stu-id="6851f-103">This sample demonstrates how to implement an HTTP-based, RPC-based service - popularly referred to as "POX" (Plain Old XML) service – using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST Programming model.</span></span> <span data-ttu-id="6851f-104">Bu örnek iki bileşenden oluşur: kendini barındıran [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP hizmet (adını da) ve hizmet oluşturur ve bunu çağrılar bir konsol uygulaması (Program.cs).</span><span class="sxs-lookup"><span data-stu-id="6851f-104">This sample consists of two components: a self-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP service (Service.cs) and a console application (Program.cs) that creates the service and makes calls to it.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="6851f-105">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="6851f-105">Sample Details</span></span>  
 <span data-ttu-id="6851f-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmet sunan 2 işlemleri `EchoWithGet` ve `EchoWithPost`, girdi olarak geçirilen dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="6851f-106">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service exposes 2 operations, `EchoWithGet` and `EchoWithPost`, which returns the string that was passed as input.</span></span>  
  
 <span data-ttu-id="6851f-107">`EchoWithGet` İşlemi açıklama ile <xref:System.ServiceModel.Web.WebGetAttribute>, belirten işlemi HTTP işler `GET` istekleri.</span><span class="sxs-lookup"><span data-stu-id="6851f-107">The `EchoWithGet` operation is annotated with <xref:System.ServiceModel.Web.WebGetAttribute>, which indicates that the operation processes HTTP `GET` requests.</span></span> <span data-ttu-id="6851f-108">Çünkü <xref:System.ServiceModel.Web.WebGetAttribute> açıkça belirtmediği bir <xref:System.UriTemplate>, ada sahip bir sorgu dizesi parametresi kullanımında geçirilecek giriş dizesi işlemi bekliyor `s`.</span><span class="sxs-lookup"><span data-stu-id="6851f-108">Because the <xref:System.ServiceModel.Web.WebGetAttribute> does not explicitly specify a <xref:System.UriTemplate>, the operation expects the input string to be passed in using a query string parameter with name `s`.</span></span> <span data-ttu-id="6851f-109">Hizmet bekliyor URI biçimi kullanılarak özelleştirilebilir Not <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="6851f-109">Note that the format of the URI that the service expects can be customized using the <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A> property.</span></span>  
  
 <span data-ttu-id="6851f-110">`EchoWithPost` İşlemi açıklama ile <xref:System.ServiceModel.Web.WebInvokeAttribute>, bunu belirten değil bir `GET` işlemi (yan etkisi yoktur).</span><span class="sxs-lookup"><span data-stu-id="6851f-110">The `EchoWithPost` operation is annotated with <xref:System.ServiceModel.Web.WebInvokeAttribute>, which indicates it is not a `GET` operation (it has side effects).</span></span> <span data-ttu-id="6851f-111">Çünkü <xref:System.ServiceModel.Web.WebInvokeAttribute> açıkça belirtmediği bir `Method`, işlemi işleyen HTTP `POST` istek gövdesinde dizesine sahip istekleri (XML biçiminde örneği için).</span><span class="sxs-lookup"><span data-stu-id="6851f-111">Because the <xref:System.ServiceModel.Web.WebInvokeAttribute> does not explicitly specify a `Method`, the operation processes HTTP `POST` requests that have the string in the request body (in the XML format, for instance).</span></span> <span data-ttu-id="6851f-112">HTTP yöntemi ve istek için URI biçimi kullanılarak özelleştirilebilir olduğunu unutmayın <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> ve <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> özellikleri sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="6851f-112">Note that the HTTP method and the format of the URI for the request can be customized using the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> and <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> properties respectively.</span></span>  
  
 <span data-ttu-id="6851f-113">App.config dosyasını WCF Hizmeti ile bir varsayılan yapılandırır <xref:System.ServiceModel.Description.WebHttpEndpoint> olan <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="6851f-113">The App.config file configures the WCF service with a default <xref:System.ServiceModel.Description.WebHttpEndpoint> that has the <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> property set to `true`.</span></span> <span data-ttu-id="6851f-114">Sonuç olarak, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] altyapıyı oluşturur otomatik bir HTML tabanlı yardım sayfasına `http://localhost:8000/Customers/help` HTTP isteklerine hizmet oluşturmak ve hizmetin HTTP yanıtı kullanma hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6851f-114">As a result, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure creates an automatic HTML based help page at `http://localhost:8000/Customers/help` that provides information about how to construct HTTP requests to the service and how to consume the service’s HTTP response.</span></span>  
  
 <span data-ttu-id="6851f-115">Program.cs gösteren nasıl bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kanal fabrikası, hizmet ve işlem yanıtları çağrı yapmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6851f-115">Program.cs demonstrates how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory can be used to make calls to the service and process responses.</span></span> <span data-ttu-id="6851f-116">Bu yalnızca bir erişmek için yolu olduğuna dikkat edin bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet.</span><span class="sxs-lookup"><span data-stu-id="6851f-116">Note that this is just one way to access a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="6851f-117">Diğer .NET Framework sınıfları gibi kullanarak hizmete erişmek mümkündür <xref:System.Net.HttpWebRequest> ve <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="6851f-117">It is also possible to access the service using other .NET Framework classes like <xref:System.Net.HttpWebRequest> and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="6851f-118">SDK'sındaki diğer örnekleri (gibi [Otomatik Biçim Seçimi](../../../../docs/framework/wcf/samples/automatic-format-selection.md) örnek ve [temel kaynak hizmeti](../../../../docs/framework/wcf/samples/basic-resource-service.md) örnek) ile iletişim kurmak için bu sınıfları kullanmayı gösteren bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet.</span><span class="sxs-lookup"><span data-stu-id="6851f-118">Other samples in the SDK (such as the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample and [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample) show how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="6851f-119">Kendini barındıran hizmet ve bir istemci örnek oluşan her ikisi içinde bir konsol uygulamasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="6851f-119">The sample consists a self-hosted service and a client that both run within a console application.</span></span> <span data-ttu-id="6851f-120">Konsol uygulaması çalışırken, istemci hizmete istek yaptığında ve konsol penceresine yanıtlardan bilgileri yazar.</span><span class="sxs-lookup"><span data-stu-id="6851f-120">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6851f-121">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="6851f-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="6851f-122">Çözümü için temel Http hizmeti örneği açın.</span><span class="sxs-lookup"><span data-stu-id="6851f-122">Open the solution for the Basic Http Service Sample.</span></span> <span data-ttu-id="6851f-123">Başlatılırken [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], başarılı bir şekilde çalıştırmak için örnek yönetici olarak çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="6851f-123">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you must run as an administrator for the sample to execute successfully.</span></span> <span data-ttu-id="6851f-124">Sağ tıklayarak bunu [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] simgesini ve seçerek **yönetici olarak çalıştır** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="6851f-124">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and selecting **Run as Administrator** from the context menu.</span></span>  
  
2.  <span data-ttu-id="6851f-125">Çözümü derlemek ve hata ayıklama olmadan konsol uygulamasını çalıştırmak için Ctrl + F5 tuşuna basın CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="6851f-125">Press CTRL+SHIFT+B to build the solution and then press Ctrl+F5 to run the console application without debugging.</span></span> <span data-ttu-id="6851f-126">Konsol penceresinde görüntülenir ve çalışan hizmetin URI sağlar ve URI HTML sayfası çalışan hizmetin için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="6851f-126">The console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="6851f-127">Herhangi bir noktada, HTML Yardım sayfasına bir tarayıcıda yardım sayfasına URI'sini yazarak görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6851f-127">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span> <span data-ttu-id="6851f-128">Örnek çalışırken, istemcinin geçerli etkinlik durumunu yazar.</span><span class="sxs-lookup"><span data-stu-id="6851f-128">As the sample runs, the client writes the status of the current activity.</span></span>  
  
3.  <span data-ttu-id="6851f-129">Örnek sonlandırmak için herhangi bir tuşa basın.</span><span class="sxs-lookup"><span data-stu-id="6851f-129">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6851f-130">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="6851f-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6851f-131">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="6851f-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6851f-132">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="6851f-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6851f-133">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="6851f-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a><span data-ttu-id="6851f-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6851f-134">See Also</span></span>  
 [<span data-ttu-id="6851f-135">Otomatik Biçim Seçimi</span><span class="sxs-lookup"><span data-stu-id="6851f-135">Automatic Format Selection</span></span>](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [<span data-ttu-id="6851f-136">Temel kaynak hizmeti</span><span class="sxs-lookup"><span data-stu-id="6851f-136">Basic Resource Service</span></span>](../../../../docs/framework/wcf/samples/basic-resource-service.md)