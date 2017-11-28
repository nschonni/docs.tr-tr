---
title: "XAML'de xml:space İşleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a5048cbad1d2ea914d041ac3c87a43223b208c3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="67389-102">XAML'de xml:space İşleme</span><span class="sxs-lookup"><span data-stu-id="67389-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="67389-103">`xml:space` Özniteliği olan bir nesne öğesi içinde önemli boşluk işleme davranışı bildiren XML tanımlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="67389-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="67389-104">Bu davranış öğesinde bulunan tüm içerik (iç metni) için ilgili nerede `xml:space` bildirilir ve ayrıca kapsamları alt öğelerine.</span><span class="sxs-lookup"><span data-stu-id="67389-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="67389-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="67389-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="67389-106">\-veya -</span><span class="sxs-lookup"><span data-stu-id="67389-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="67389-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="67389-107">Remarks</span></span>  
 <span data-ttu-id="67389-108">Tanımı `xml:space` olası iki değeri de dahil olmak üzere XAML'de özniteliği türetilir `xml:space` "özel özniteliği" XML için W3C belirtimleri tarafından tanımlanan.</span><span class="sxs-lookup"><span data-stu-id="67389-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="67389-109">Varsayılan değer olan `xml:space` hazır değeri bir özniteliktir `"default"`.</span><span class="sxs-lookup"><span data-stu-id="67389-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="67389-110">Değeri için `"default"`, veya `xml:space` önemli boşluk ayrıştırma davranışını konusundaki tanımlanan varsayılan işleme olduğundan hiç belirtilmemiş [XAML'de boşluk işleme](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="67389-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="67389-111">İçinde nesne öğe içeriği korumak için belirtmek `xml:space="preserve"` bu nesne öğede.</span><span class="sxs-lookup"><span data-stu-id="67389-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="67389-112">Çoğu yorumlar altında `xml:space` özniteliği etkiler ve özniteliğinin değeri alt öğelerine kapsamlı.</span><span class="sxs-lookup"><span data-stu-id="67389-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="67389-113">XAML'de boşluk işleme kapsamlı bir açıklama için bkz: [XAML'de boşluk işleme](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="67389-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67389-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="67389-114">See Also</span></span>  
 [<span data-ttu-id="67389-115">XAML'de boşluk işleme</span><span class="sxs-lookup"><span data-stu-id="67389-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="67389-116">XAML genel bakış (WPF)</span><span class="sxs-lookup"><span data-stu-id="67389-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)