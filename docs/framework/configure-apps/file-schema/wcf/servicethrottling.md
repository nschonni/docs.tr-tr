---
title: '&lt;serviceThrottling&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6ba0f3a442e3598322f223be63b64a811c8f785a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="7b603-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="7b603-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="7b603-103">Windows Communication Foundation (WCF) hizmetini azaltma mekanizmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="7b603-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="7b603-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7b603-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b603-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="7b603-105">\<behaviors></span></span>  
<span data-ttu-id="7b603-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7b603-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7b603-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="7b603-107">\<behavior></span></span>  
<span data-ttu-id="7b603-108">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="7b603-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b603-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7b603-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b603-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7b603-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7b603-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7b603-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b603-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7b603-112">Attributes</span></span>  
  
|<span data-ttu-id="7b603-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="7b603-113">Attribute</span></span>|<span data-ttu-id="7b603-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7b603-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b603-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="7b603-115">maxConcurrentCalls</span></span>|<span data-ttu-id="7b603-116">Şu anda arasında işlem iletilerinin sayısını sınırlar pozitif bir tamsayı bir <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7b603-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7b603-117">Sınırı aşan çağrıları kuyruğa alınır.</span><span class="sxs-lookup"><span data-stu-id="7b603-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="7b603-118">Bu değerin 0 olarak ayarlanması, Int32.MaxValue olarak ayarlamaya eşittir.</span><span class="sxs-lookup"><span data-stu-id="7b603-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="7b603-119">16 varsayılandır * işlemci sayısı.</span><span class="sxs-lookup"><span data-stu-id="7b603-119">The default is 16 * processor count.</span></span>|  
|<span data-ttu-id="7b603-120">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="7b603-120">maxConcurrentInstances</span></span>|<span data-ttu-id="7b603-121">Sayısını sınırlayan bir pozitif tamsayı <xref:System.ServiceModel.InstanceContext> arasında aynı anda yürütme nesneleri bir <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7b603-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7b603-122">Ek örnekleri oluşturmak için istekler kuyruğa alınır ve sınırın altındaki bir yuva kullanılabilir hale geldiğinde tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="7b603-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="7b603-123">Varsayılan maxConcurrentSessions ve MaxConcurrentCalls toplamıdır</span><span class="sxs-lookup"><span data-stu-id="7b603-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="7b603-124">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="7b603-124">maxConcurrentSessions</span></span>|<span data-ttu-id="7b603-125">Oturum sayısını sınırlar pozitif bir tamsayı bir <xref:System.ServiceModel.ServiceHost> nesnesini kabul edebilir.</span><span class="sxs-lookup"><span data-stu-id="7b603-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="7b603-126">Hizmet sınırı aşan bağlantılarını kabul eder, ancak yalnızca sınırın altındaki kanalları etkin (kanaldan iletiler okunur).</span><span class="sxs-lookup"><span data-stu-id="7b603-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="7b603-127">Bu değerin 0 olarak ayarlanması, Int32.MaxValue olarak ayarlamaya eşittir.</span><span class="sxs-lookup"><span data-stu-id="7b603-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="7b603-128">Varsayılan değer 100'dür * işlemci sayısı.</span><span class="sxs-lookup"><span data-stu-id="7b603-128">The default is 100 * processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b603-129">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7b603-129">Child Elements</span></span>  
 <span data-ttu-id="7b603-130">Yok.</span><span class="sxs-lookup"><span data-stu-id="7b603-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b603-131">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7b603-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7b603-132">Öğe</span><span class="sxs-lookup"><span data-stu-id="7b603-132">Element</span></span>|<span data-ttu-id="7b603-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7b603-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b603-134">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="7b603-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7b603-135">Bir davranış öğesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="7b603-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b603-136">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7b603-136">Remarks</span></span>  
 <span data-ttu-id="7b603-137">Azaltma denetimleri sınırlarını eşzamanlı çağrıları, örneği veya oturumları atlayarak kaynaklarının kullanımını engellemek için sayısına yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="7b603-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="7b603-138">Özniteliklerin değeri ulaşıldığında her zaman bir izleme yazılır.</span><span class="sxs-lookup"><span data-stu-id="7b603-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="7b603-139">İlk izleme uyarı olarak yazılır.</span><span class="sxs-lookup"><span data-stu-id="7b603-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b603-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="7b603-140">Example</span></span>  
 <span data-ttu-id="7b603-141">Aşağıdaki yapılandırma örneği hizmet 2 ile 10 eşzamanlı örnek sayısı maksimum eşzamanlı çağrı sınırları belirtir.</span><span class="sxs-lookup"><span data-stu-id="7b603-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="7b603-142">Bu örnekte çalışan ayrıntılı örnek için bkz: [azaltma](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="7b603-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b603-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7b603-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="7b603-144">Denetlemek için WCF hizmet performansını ServiceThrottlingBehavior kullanma</span><span class="sxs-lookup"><span data-stu-id="7b603-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)