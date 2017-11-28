---
title: '&lt;defaultPorts&gt; &lt;ekleme&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd487238ebe327a5f89b737fdf764d94f955a411
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="45336-102">&lt;defaultPorts&gt; &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="45336-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="45336-103">İstemci uygulaması dinlediği bir varsayılan iletişim uç noktası.</span><span class="sxs-lookup"><span data-stu-id="45336-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="45336-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="45336-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45336-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="45336-105">\<behaviors></span></span>  
<span data-ttu-id="45336-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45336-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="45336-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="45336-107">\<behavior></span></span>  
<span data-ttu-id="45336-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="45336-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="45336-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="45336-109">\<defaultPorts></span></span>  
<span data-ttu-id="45336-110">\<ekleme ></span><span class="sxs-lookup"><span data-stu-id="45336-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45336-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="45336-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45336-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="45336-112">Attributes and Elements</span></span>  
 <span data-ttu-id="45336-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="45336-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45336-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="45336-114">Attributes</span></span>  
  
|<span data-ttu-id="45336-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="45336-115">Attribute</span></span>|<span data-ttu-id="45336-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="45336-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45336-117">bağlantı noktası</span><span class="sxs-lookup"><span data-stu-id="45336-117">port</span></span>|<span data-ttu-id="45336-118">Varsayılan iletişim bağlantı noktası numarası belirten bir tamsayı</span><span class="sxs-lookup"><span data-stu-id="45336-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="45336-119">düzen</span><span class="sxs-lookup"><span data-stu-id="45336-119">scheme</span></span>|<span data-ttu-id="45336-120">Bir iletişim bağlantı noktası ile ilişkili protokolü ayarları grubu belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="45336-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45336-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="45336-121">Child Elements</span></span>  
 <span data-ttu-id="45336-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="45336-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45336-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="45336-123">Parent Elements</span></span>  
  
|<span data-ttu-id="45336-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="45336-124">Element</span></span>|<span data-ttu-id="45336-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="45336-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45336-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="45336-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="45336-127">İstemci uygulaması dinlediği varsayılan iletişim uç noktalarını listeleme varsayılan bağlantı noktaları koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="45336-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45336-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="45336-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>