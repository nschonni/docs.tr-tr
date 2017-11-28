---
title: WCF Veri Hizmetleri 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1ef95ac84872b2cc39ec3a93abab10c39cd7738
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="ed2a5-102">WCF Veri Hizmetleri 4.5</span><span class="sxs-lookup"><span data-stu-id="ed2a5-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ed2a5-103">(eski adıyla "ADO.NET Veri Hizmetleri") kullanan hizmetler oluşturmanızı sağlayan .NET Framework'ün bir bileşen olan [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] semantiği kullanarak Web veya intranet üzerinden verileri kullanmak ve kullanıma sunmak için [temsili durum Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="ed2a5-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="ed2a5-104">Veri URI tarafından adreslenebilir kaynakları olarak kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="ed2a5-105">Veriler erişilen ve GET, PUT, POST ve DELETE standart HTTP fiillerini kullanarak değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="ed2a5-106">Varlık ilişkisi kuralları kullanan [varlık veri modeli](../../../../docs/framework/data/adonet/entity-data-model.md) kaynaklara göre ilişkileri ilişkili varlık kümesi olarak kullanıma sunmak için.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ed2a5-107">kullanan [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] adresleme ve kaynakları güncelleştirmek için protokol.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="ed2a5-108">Bu şekilde, bu hizmetleri destekleyen herhangi bir istemciden erişebilirsiniz [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed2a5-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="ed2a5-109">İstek ve bilinen aktarımı biçimlerini kullanarak veri kaynaklarına yazma sağlar: Atom, değişim ve verileri XML ve JavaScript nesne gösterimi (JSON) güncelleştirme standartlarını kümesi AJAX uygulamada yaygın olarak kullanılan metin tabanlı veri exchange biçimi.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ed2a5-110">çeşitli kaynaklardan kaynaklanan veri getirebilir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akışları.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="ed2a5-111">Visual Studio Araçları kolaylaştırmak oluşturmak için bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-bir ADO.NET Entity Framework veri modeli kullanarak hizmet tabanlı.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="ed2a5-112">Ayrıca oluşturabilirsiniz [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ortak dil çalışma zamanı (CLR) sınıfları ve hatta geç bağlama veya türsüz veri akışları bağlı.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ed2a5-113">Ayrıca istemci kitaplıkları, biri genel .NET Framework istemci uygulamaları için diğeri Silverlight tabanlı uygulamalar için özel olarak bir dizi içerir.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="ed2a5-114">Siz eriştiğinizde, bu istemci kitaplıkları, nesne tabanlı programlama modeli sağlar. bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] .NET Framework ve Silverlight gibi ortamlarından akış.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="ed2a5-115">Nereden başlamalıyım?</span><span class="sxs-lookup"><span data-stu-id="ed2a5-115">Where Should I Start?</span></span>  
 <span data-ttu-id="ed2a5-116">İle çalışmaya başlama alanlarınızı bağlı olarak göz önünde bulundurun [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] aşağıdaki konulardan birindeki.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="ed2a5-117">Hemen istediğiniz...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="ed2a5-118">Hızlı Başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-119">Başlarken</span><span class="sxs-lookup"><span data-stu-id="ed2a5-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-120">Silverlight hızlı başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="ed2a5-121">Windows Phone geliştirme için Silverlight hızlı başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="ed2a5-122">Yalnızca bazı kodlar göster...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="ed2a5-123">Hızlı Başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-124">Nasıl yapılır: veri hizmeti sorgularını Yürüt</span><span class="sxs-lookup"><span data-stu-id="ed2a5-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-125">Nasıl yapılır: Windows Presentation Foundation öğelerine veri bağlama</span><span class="sxs-lookup"><span data-stu-id="ed2a5-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="ed2a5-126">Daha fazla bilgi almak istiyorum [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="ed2a5-127">Teknik İnceleme: OData Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="ed2a5-128">Açık Veri Protokolü Web sitesi</span><span class="sxs-lookup"><span data-stu-id="ed2a5-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="ed2a5-129">OData: SDK'sı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="ed2a5-130">OData: Sık sorulan sorular</span><span class="sxs-lookup"><span data-stu-id="ed2a5-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="ed2a5-131">Bazı videolar izlemek istediğiniz...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="ed2a5-132">WCF Veri Hizmetleri için Başlangıç Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="ed2a5-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="ed2a5-133">Geliştirici videolar WCF Veri Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="ed2a5-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="ed2a5-134">OData: Geliştiricilerin Web sitesi</span><span class="sxs-lookup"><span data-stu-id="ed2a5-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="ed2a5-135">Uçtan uca örnekleri görmek istiyorum</span><span class="sxs-lookup"><span data-stu-id="ed2a5-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="ed2a5-136">MSDN Örnekler Galerisi belgelerine örnekleri WCF Veri Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="ed2a5-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="ed2a5-137">MSDN Örnekler Galerisi örnekleri diğer WCF Veri Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="ed2a5-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="ed2a5-138">OData: SDK'sı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="ed2a5-139">Bu Visual Studio ile nasıl tümleştiriliyor?</span><span class="sxs-lookup"><span data-stu-id="ed2a5-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="ed2a5-140">Veri Hizmeti istemci kitaplığı oluşturma</span><span class="sxs-lookup"><span data-stu-id="ed2a5-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-141">Veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="ed2a5-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="ed2a5-142">Entity Framework sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="ed2a5-143">Bununla ne yapabilirim?</span><span class="sxs-lookup"><span data-stu-id="ed2a5-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="ed2a5-144">Genel bakış</span><span class="sxs-lookup"><span data-stu-id="ed2a5-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="ed2a5-145">Teknik İnceleme: OData Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="ed2a5-146">Uygulama senaryoları</span><span class="sxs-lookup"><span data-stu-id="ed2a5-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="ed2a5-147">Silverlight kullanmak istediğiniz...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="ed2a5-148">Silverlight hızlı başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="ed2a5-149">WCF Veri Hizmetleri (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="ed2a5-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="ed2a5-150">Silverlight ile çalışmaya başlama</span><span class="sxs-lookup"><span data-stu-id="ed2a5-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="ed2a5-151">Bir Windows Phone uygulaması oluşturmak istediğiniz...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="ed2a5-152">Windows Phone geliştirme için Silverlight hızlı başlangıç</span><span class="sxs-lookup"><span data-stu-id="ed2a5-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="ed2a5-153">Windows Phone için açık veri Protokolü (OData) istemcisi</span><span class="sxs-lookup"><span data-stu-id="ed2a5-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="ed2a5-154">LINQ kullanmak istediğiniz...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="ed2a5-155">Veri Hizmeti sorgulama</span><span class="sxs-lookup"><span data-stu-id="ed2a5-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-156">LINQ hakkında önemli noktalar</span><span class="sxs-lookup"><span data-stu-id="ed2a5-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="ed2a5-157">Nasıl yapılır: veri hizmeti sorgularını Yürüt</span><span class="sxs-lookup"><span data-stu-id="ed2a5-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="ed2a5-158">Hala bazı ek bilgiler ihtiyacım...</span><span class="sxs-lookup"><span data-stu-id="ed2a5-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="ed2a5-159">WCF Veri Hizmetleri ekibi Web günlüğü</span><span class="sxs-lookup"><span data-stu-id="ed2a5-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="ed2a5-160">Kaynakları</span><span class="sxs-lookup"><span data-stu-id="ed2a5-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="ed2a5-161">WCF Veri Hizmetleri Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="ed2a5-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="ed2a5-162">Açık Veri Protokolü Web sitesi</span><span class="sxs-lookup"><span data-stu-id="ed2a5-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="ed2a5-163">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="ed2a5-163">In This Section</span></span>  
 [<span data-ttu-id="ed2a5-164">Genel bakış</span><span class="sxs-lookup"><span data-stu-id="ed2a5-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="ed2a5-165">Özellikleri ve işlevleri kullanılabilen genel bir bakış sağlar [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed2a5-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="ed2a5-166">WCF Veri Hizmetleri yenilikleri</span><span class="sxs-lookup"><span data-stu-id="ed2a5-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="ed2a5-167">Yeni işlevsellik açıklanmaktadır [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ve yeni desteği [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] özellikleri.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="ed2a5-168">Başlarken</span><span class="sxs-lookup"><span data-stu-id="ed2a5-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="ed2a5-169">Kullanıma ve kullanmayı açıklar [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akışları kullanarak [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed2a5-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="ed2a5-170">WCF veri hizmetleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="ed2a5-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="ed2a5-171">Oluşturma ve kullanıma sunan bir veri hizmeti yapılandırma açıklanır [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akışları.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="ed2a5-172">WCF Veri Hizmetleri İstemci Kitaplığı</span><span class="sxs-lookup"><span data-stu-id="ed2a5-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="ed2a5-173">Kullanmak için istemci kitaplıkları kullanmayı açıklar [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akışları bir .NET Framework istemci uygulamasından.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed2a5-174">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ed2a5-174">See Also</span></span>  
 [<span data-ttu-id="ed2a5-175">Temsili durum aktarımı (REST)</span><span class="sxs-lookup"><span data-stu-id="ed2a5-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)