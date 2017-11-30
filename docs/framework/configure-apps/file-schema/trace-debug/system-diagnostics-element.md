---
title: "&lt;System.Diagnostics&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d336a0f733451cb28d8fe57af20585515b71ca4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemdiagnosticsgt-element"></a><span data-ttu-id="4fb42-102">&lt;System.Diagnostics&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="4fb42-102">&lt;system.diagnostics&gt; Element</span></span>
<span data-ttu-id="4fb42-103">Toplamak, depolamak ve iletileri ve izleme anahtarı ayarlandığı düzeyi rota izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="4fb42-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="4fb42-104">\<configuration></span></span>  
<span data-ttu-id="4fb42-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4fb42-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb42-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4fb42-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fb42-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="4fb42-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4fb42-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4fb42-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fb42-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="4fb42-109">Attributes</span></span>  
 <span data-ttu-id="4fb42-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="4fb42-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fb42-111">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="4fb42-111">Child Elements</span></span>  
  
|<span data-ttu-id="4fb42-112">Öğe</span><span class="sxs-lookup"><span data-stu-id="4fb42-112">Element</span></span>|<span data-ttu-id="4fb42-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4fb42-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fb42-114">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="4fb42-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="4fb42-115">Bir ileti kutusu çağırdığınızda görüntülenip görüntülenmeyeceğini belirtir <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> yöntemi; ayrıca iletileri yazmak için dosya adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="4fb42-116">\<performans sayaçları ></span><span class="sxs-lookup"><span data-stu-id="4fb42-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="4fb42-117">Performans sayaçları tarafından paylaşılan genel bellek boyutunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="4fb42-118">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="4fb42-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="4fb42-119">Herhangi bir kaynak veya trace ögesi başvurabilir dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="4fb42-120">Paylaşılan dinleyiciler tanımlanan dinleyicileri kaynakları veya izlemeleri adıyla eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="4fb42-121">\<Kaynakları ></span><span class="sxs-lookup"><span data-stu-id="4fb42-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="4fb42-122">İzleme iletileri başlatmak izleme kaynakları belirtir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="4fb42-123">\<anahtarları ></span><span class="sxs-lookup"><span data-stu-id="4fb42-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="4fb42-124">İzleme anahtarları ve izleme anahtarları belirlendiği düzeyleri içerir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="4fb42-125">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="4fb42-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="4fb42-126">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="4fb42-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fb42-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="4fb42-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4fb42-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="4fb42-128">Element</span></span>|<span data-ttu-id="4fb42-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4fb42-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4fb42-130">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="4fb42-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4fb42-131">Örnek</span><span class="sxs-lookup"><span data-stu-id="4fb42-131">Example</span></span>  
 <span data-ttu-id="4fb42-132">Aşağıdaki örnek, bir izleme anahtarı ve İzleme dinleyicisi içindeki katıştırmak gösterilmiştir  **\<system.diagnostics >** öğesi.</span><span class="sxs-lookup"><span data-stu-id="4fb42-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="4fb42-133">`General` İzleme anahtarı ayarlanmış <xref:System.Diagnostics.TraceLevel> düzeyi.</span><span class="sxs-lookup"><span data-stu-id="4fb42-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="4fb42-134">İzleme dinleyicisi `myListener` adlı bir dosya oluşturur `MyListener.log` ve çıkış dosyasına yazar.</span><span class="sxs-lookup"><span data-stu-id="4fb42-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fb42-135">.NET Framework sürüm 2. 0'da, bir anahtar değeri belirtmek için metin kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4fb42-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="4fb42-136">Örneğin, belirtebilirsiniz `true` için bir <xref:System.Diagnostics.BooleanSwitch> veya bir numaralandırma değeri gibi temsil eden metin `Error` için bir <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="4fb42-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="4fb42-137">Satır `<add name="myTraceSwitch" value="Error" />` eşdeğerdir `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="4fb42-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fb42-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4fb42-138">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="4fb42-139">İzleme ve hata ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="4fb42-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)