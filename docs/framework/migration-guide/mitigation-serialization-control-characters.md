---
title: "Azaltma: Serileştirme DataContractJsonSerializer ile denetim karakterleri"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6da580d208736a64e2094f701fb4c1241a488322
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="b3205-102">Azaltma: Serileştirme DataContractJsonSerializer ile denetim karakterleri</span><span class="sxs-lookup"><span data-stu-id="b3205-102">Mitigation: Serialization of Control Characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="b3205-103">.NET Framework 4.7 ile hangi denetiminde karakter ile serileştirilir şekilde başlangıç <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ECMAScript V6 ve V8 uygun olarak değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="b3205-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="b3205-104">Etki</span><span class="sxs-lookup"><span data-stu-id="b3205-104">Impact</span></span>

<span data-ttu-id="b3205-105">.NET framework 4.6.2 ve önceki sürümlerde, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> bazı özel denetim karakterleri gibi seri değil `\b`, `\f`, ve `\t`, ECMAScript V6 ve V8 standartlarla uyumlu bir biçimde.</span><span class="sxs-lookup"><span data-stu-id="b3205-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="b3205-106">.NET Framework 4.7 ile başlayan .NET Framework sürümlerini hedefleyen uygulamalar için bu denetim karakterleri serileştirmek ECMAScript V6 ve V8 ile uyumludur.</span><span class="sxs-lookup"><span data-stu-id="b3205-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="b3205-107">Aşağıdaki API'leri etkilenir:</span><span class="sxs-lookup"><span data-stu-id="b3205-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="b3205-108">Azaltma</span><span class="sxs-lookup"><span data-stu-id="b3205-108">Mitigation</span></span>

<span data-ttu-id="b3205-109">.NET Framework 4.7 ile başlayan .NET Framework sürümlerini hedefleyen uygulamalar için bu davranışı varsayılan olarak etkindir.</span><span class="sxs-lookup"><span data-stu-id="b3205-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="b3205-110">Bu davranış arzu değilse, aşağıdaki satırı ekleyerek dışında bu özellik seçebilirsiniz `<runtime>` app.config veya web.config dosyasının:</span><span class="sxs-lookup"><span data-stu-id="b3205-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="b3205-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b3205-111">See also</span></span>
[<span data-ttu-id="b3205-112">.NET Framework 4.7 yeniden hedefleme değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="b3205-112">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)