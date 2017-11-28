---
title: '&lt;kimlik&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa6bfdf72bd292599867bf7a9571ecd6b408a2c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="70076-102">&lt;kimlik&gt;</span><span class="sxs-lookup"><span data-stu-id="70076-102">&lt;identity&gt;</span></span>
<span data-ttu-id="70076-103">Kimlik öğesi tasarım zamanında hizmet beklenen kimliğini belirtmek bir istemci Geliştirici sağlar.</span><span class="sxs-lookup"><span data-stu-id="70076-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="70076-104">İstemci ile hizmet arasında el sıkışma işleminde [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] altyapı beklenen hizmet kimliğini bu öğenin değerlerle eşleştiğinden ve böylece doğrulanabilir emin olun.</span><span class="sxs-lookup"><span data-stu-id="70076-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="70076-105">Daha fazla bilgi için bkz: [hizmet kimliği ve kimlik doğrulama](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="70076-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="70076-106">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="70076-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="70076-107">\<İstemci ></span><span class="sxs-lookup"><span data-stu-id="70076-107">\<client></span></span>  
<span data-ttu-id="70076-108">\<uç noktası ></span><span class="sxs-lookup"><span data-stu-id="70076-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70076-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="70076-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70076-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="70076-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70076-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="70076-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70076-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="70076-112">Attributes</span></span>  
 <span data-ttu-id="70076-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="70076-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70076-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="70076-114">Child Elements</span></span>  
  
|<span data-ttu-id="70076-115">Öğe</span><span class="sxs-lookup"><span data-stu-id="70076-115">Element</span></span>|<span data-ttu-id="70076-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70076-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70076-117">sertifika</span><span class="sxs-lookup"><span data-stu-id="70076-117">certificate</span></span>|<span data-ttu-id="70076-118">Bir X.509 sertifikası ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="70076-119">Bu öğe türünde <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="70076-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="70076-120">Bir öznitelik içeriyor `encodedValue` diğer bir deyişle bu sertifika tarafından kodlanmış değeri belirten bir dize,.</span><span class="sxs-lookup"><span data-stu-id="70076-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="70076-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="70076-121">certificateReference</span></span>|<span data-ttu-id="70076-122">X.509 Sertifika doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="70076-123">Bu öğe türünde <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="70076-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="70076-124">dns</span><span class="sxs-lookup"><span data-stu-id="70076-124">dns</span></span>|<span data-ttu-id="70076-125">Bir hizmetin kimliğini doğrulamak için kullanılan bir X.509 sertifikası DNS belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="70076-126">Bu öğe bir öznitelik içeriyor `value` , bir dizedir ve gerçek kimliğini içerir.</span><span class="sxs-lookup"><span data-stu-id="70076-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="70076-127">rsa</span><span class="sxs-lookup"><span data-stu-id="70076-127">rsa</span></span>|<span data-ttu-id="70076-128">Bir hizmet için bir istemci kimlik doğrulaması için kullanılan bir X.509 sertifikası RSA alanının değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="70076-129">Bu öğe bir öznitelik içeriyor `value` , bir dizedir ve gerçek kimliğini içerir</span><span class="sxs-lookup"><span data-stu-id="70076-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="70076-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="70076-130">servicePrincipalName</span></span>|<span data-ttu-id="70076-131">Bir hizmet örneğini benzersiz şekilde tanımlamak için bir istemci tarafından kullanılan asıl ad sunucu asıl adı (SPN) kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="70076-132">Bu öğe bir öznitelik içeriyor `value` , bir dizedir ve gerçek asıl adını içerir.</span><span class="sxs-lookup"><span data-stu-id="70076-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="70076-133">Bu öğe türünde <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="70076-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="70076-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="70076-134">userPrincipalName</span></span>|<span data-ttu-id="70076-135">Bir kullanıcı ağda oturum açma adı türünde bir kullanıcı asıl adı (UPN) kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="70076-136">Ardından, Active Directory içinde kullanılan kullanıcı nesne adı, kullanıcı asıl adı oluşur simgesini (@) ve ardından, genellikle, etki alanı adı sistemi üst etki alanı.</span><span class="sxs-lookup"><span data-stu-id="70076-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="70076-137">Örneğin, kullanıcı asıl adı Jeff Fabrikam.com etki alanı ağacındaki olabilir [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Bu öğe bir öznitelik içeriyor `value` , bir dizedir ve gerçek asıl adını içerir.</span><span class="sxs-lookup"><span data-stu-id="70076-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="70076-138">Bu öğe türünde <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="70076-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70076-139">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="70076-139">Parent Elements</span></span>  
  
|<span data-ttu-id="70076-140">Öğe</span><span class="sxs-lookup"><span data-stu-id="70076-140">Element</span></span>|<span data-ttu-id="70076-141">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70076-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70076-142">\<Özel ></span><span class="sxs-lookup"><span data-stu-id="70076-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="70076-143">Bir netPeerTcpBinding için özel eş çözümleyici belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="70076-144">\<uç noktası ></span><span class="sxs-lookup"><span data-stu-id="70076-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="70076-145">Farklı türde uç noktalar yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="70076-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="70076-146">\<veren ></span><span class="sxs-lookup"><span data-stu-id="70076-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="70076-147">Güvenlik belirteci hizmeti (STS) Federasyon Hizmeti için belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="70076-148">\<İssuedtokenparameters ></span><span class="sxs-lookup"><span data-stu-id="70076-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="70076-149">Güvenlik belirteci hizmeti (STS için) Federasyon Hizmeti meta veri uç noktasının belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="70076-150">\<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="70076-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="70076-151">İçinde özel bağlama verilen bir belirteç parametrelerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="70076-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="70076-152">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="70076-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="70076-153">Bir yerel güvenlik belirteci hizmeti (STS) belirtir.</span><span class="sxs-lookup"><span data-stu-id="70076-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70076-154">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70076-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="70076-155">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="70076-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="70076-156">Uç noktalar: Adresler, bağlamalar ve sözleşmeler</span><span class="sxs-lookup"><span data-stu-id="70076-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)