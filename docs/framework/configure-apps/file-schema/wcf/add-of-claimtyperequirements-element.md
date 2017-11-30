---
title: "&lt;claimTypeRequirements&gt; öğesi &lt;ekleme&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0b814f7db727cba289ae6f9eba1b0c6532b52ebb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="8650b-102">&lt;claimTypeRequirements&gt; öğesi &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="8650b-102">&lt;add&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="8650b-103">Federe kimlik bilgisi görünmesi beklenen gerekli ve isteğe bağlı talep türlerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="8650b-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="8650b-104">Örneğin, belirli bir talep türleri kümesini sahip olması gerekir gelen kimlik bilgilerini gereksinimleri Hizmetleri durumu.</span><span class="sxs-lookup"><span data-stu-id="8650b-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="8650b-105">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8650b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8650b-106">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="8650b-106">\<bindings></span></span>  
<span data-ttu-id="8650b-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="8650b-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="8650b-108">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="8650b-108">\<binding></span></span>  
<span data-ttu-id="8650b-109">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="8650b-109">\<security></span></span>  
<span data-ttu-id="8650b-110">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="8650b-110">\<message></span></span>  
<span data-ttu-id="8650b-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="8650b-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8650b-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8650b-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <add claimType="URI"  
        isOptional="Boolean" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8650b-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="8650b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8650b-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8650b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8650b-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="8650b-115">Attributes</span></span>  
  
|<span data-ttu-id="8650b-116">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="8650b-116">Attribute</span></span>|<span data-ttu-id="8650b-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8650b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8650b-118">claimType</span><span class="sxs-lookup"><span data-stu-id="8650b-118">claimType</span></span>|<span data-ttu-id="8650b-119">Bir talep türünü tanımlayan bir URI.</span><span class="sxs-lookup"><span data-stu-id="8650b-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="8650b-120">Örneğin, bir Web sitesinden bir ürün satın almak için kullanıcının yeterli kredi limiti ile geçerli bir kredi kartı sunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8650b-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="8650b-121">Talep türü URI kredi kartı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="8650b-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="8650b-122">isteğe bağlıdır</span><span class="sxs-lookup"><span data-stu-id="8650b-122">isOptional</span></span>|<span data-ttu-id="8650b-123">Bunun için isteğe bağlı bir talep olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="8650b-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="8650b-124">Bu öznitelik ayarlanırsa `false` bu gerekli bir talep ise.</span><span class="sxs-lookup"><span data-stu-id="8650b-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="8650b-125">Hizmet için bazı bilgiler ister, ancak gerekli olmadığı durumlarda bu özniteliği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8650b-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="8650b-126">Örneğin, kullanıcının ilk adını girmesini gerektiriyorsa, ad ve adres son ancak telefon numarası isteğe bağlı olduğuna karar.</span><span class="sxs-lookup"><span data-stu-id="8650b-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8650b-127">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="8650b-127">Child Elements</span></span>  
 <span data-ttu-id="8650b-128">Yok.</span><span class="sxs-lookup"><span data-stu-id="8650b-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8650b-129">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="8650b-129">Parent Elements</span></span>  
  
|<span data-ttu-id="8650b-130">Öğe</span><span class="sxs-lookup"><span data-stu-id="8650b-130">Element</span></span>|<span data-ttu-id="8650b-131">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8650b-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8650b-132">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="8650b-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="8650b-133">Gerekli talep türleri koleksiyonunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="8650b-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="8650b-134">Her öğe türünde <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="8650b-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="8650b-135">Federe senaryolarda hizmetleri gelen kimlik bilgilerini gereksinimleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="8650b-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8650b-136">Örneğin, gelen kimlik bilgileri, belirli bir talep türleri kümesini sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8650b-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8650b-137">Bu koleksiyondaki her öğe bir federe kimlik bilgisi görünmesi beklenen gerekli ve isteğe bağlı talep türlerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="8650b-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8650b-138">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8650b-138">Remarks</span></span>  
 <span data-ttu-id="8650b-139">Federe senaryolarda hizmetleri gelen kimlik bilgilerini gereksinimleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="8650b-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8650b-140">Örneğin, gelen kimlik bilgileri, belirli bir talep türleri kümesini sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8650b-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8650b-141">Bu gereksinim, bir güvenlik ilkesi bildirilmiş.</span><span class="sxs-lookup"><span data-stu-id="8650b-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="8650b-142">Federasyon Hizmeti gereksinimlerini buna göre uygun kimlik bilgilerini vermek için istemci istekleri kimlik bilgileri, Federasyon Hizmeti (örneğin, CardSpace) bir belirteç isteğini (RequestSecurityToken) gereksinimlerini koyar.</span><span class="sxs-lookup"><span data-stu-id="8650b-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8650b-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="8650b-143">Example</span></span>  
 <span data-ttu-id="8650b-144">Aşağıdaki yapılandırma, güvenlik bağlamaya iki talep türü gereksinimlerini ekler.</span><span class="sxs-lookup"><span data-stu-id="8650b-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>  
    <wsFederationHttpBinding>  
      <binding name="myFederatedBinding">  
        <security mode="Message">  
          <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">  
            <claimTypeRequirements>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress"/>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"    
optional="true" />  
            </claims>  
          </message>  
        </security>  
      </binding>  
    </wsFederationHttpBinding>  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8650b-145">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8650b-145">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>