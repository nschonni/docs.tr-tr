---
title: "Nasıl yapılır: bir ADO.NET Entity Framework Veri kaynağı (WCF Veri Hizmetleri) kullanarak bir veri hizmeti oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d69a3cf60b60806085a9bb7ae292cc88ba99871e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="cbbda-102">Nasıl yapılır: bir ADO.NET Entity Framework Veri kaynağı (WCF Veri Hizmetleri) kullanarak bir veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="cbbda-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="cbbda-103">varlık verilerini veri hizmet olarak sunar.</span><span class="sxs-lookup"><span data-stu-id="cbbda-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="cbbda-104">Bu varlık verilerini tarafından sağlanan [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] veri kaynağı bir ilişkisel veritabanı olduğunda.</span><span class="sxs-lookup"><span data-stu-id="cbbda-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="cbbda-105">Bu konuda nasıl oluşturulacağını gösterir bir [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-veri modelinde dayalı bir [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web uygulaması varolan bir veritabanını temel alan ve yeni bir veri hizmeti oluşturmak için bu veri modelini kullanır.</span><span class="sxs-lookup"><span data-stu-id="cbbda-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="cbbda-106">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Oluşturabilen bir komut satırı aracı da sağlar bir [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model dışında bir [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] projesi.</span><span class="sxs-lookup"><span data-stu-id="cbbda-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="cbbda-107">Daha fazla bilgi için bkz: [nasıl yapılır: dosya eşleme ve Model oluşturmak için kullanım EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="cbbda-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="cbbda-108">Mevcut bir Web uygulamasını mevcut bir veritabanına dayalı bir Entity Framework modelini eklemek için</span><span class="sxs-lookup"><span data-stu-id="cbbda-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="cbbda-109">Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="cbbda-110">İçinde **şablonları** bölmesinde tıklatın **veri** kategori ve ardından **ADO.NET varlık veri modeli**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="cbbda-111">Model adını yazın ve ardından **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="cbbda-112">Sihirbazın ilk sayfasında [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Sihirbazı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="cbbda-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="cbbda-113">İçinde **Model içeriği seçin** iletişim kutusunda **veritabanından Oluştur**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="cbbda-114">Sonra **İleri**'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="cbbda-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="cbbda-115">Tıklatın **yeni bağlantı** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="cbbda-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="cbbda-116">İçinde **bağlantı özelliklerini** iletişim kutusu, sunucunuzun adını yazın, kimlik doğrulama yöntemi seçin, veritabanı adını yazın ve ardından **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cbbda-117">**Veri bağlantınızı**s iletişim kutusunda, veritabanı bağlantı ayarlarınızı ile güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="cbbda-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="cbbda-118">Emin **varlık bağlantı ayarlarını App.Config'de şöyle Kaydet:** onay kutusu işaretli.</span><span class="sxs-lookup"><span data-stu-id="cbbda-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="cbbda-119">Sonra **İleri**'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="cbbda-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="cbbda-120">İçinde **veritabanı nesnelerinizi** veritabanının Tümünü Seç iletişim kutusunda, nesneler veri hizmeti kullanıma sunmak planlama.</span><span class="sxs-lookup"><span data-stu-id="cbbda-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cbbda-121">Veri modelinde bulunan nesneleri veri hizmeti tarafından otomatik olarak açık değildir.</span><span class="sxs-lookup"><span data-stu-id="cbbda-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="cbbda-122">Hizmet tarafından açıkça sunulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cbbda-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="cbbda-123">Daha fazla bilgi için bkz: [veri hizmeti yapılandırma](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cbbda-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="cbbda-124">Tıklatın **son** Sihirbazı tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="cbbda-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="cbbda-125">Bu, belirli bir veritabanını temel alan bir varsayılan veri modeli oluşturur.</span><span class="sxs-lookup"><span data-stu-id="cbbda-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="cbbda-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Veri modelini özelleştirmek için etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="cbbda-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="cbbda-127">Daha fazla bilgi için bkz: [görevleri](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="cbbda-127">For more information, see [Tasks](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="cbbda-128">Yeni veri modelini kullanarak veri hizmeti oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="cbbda-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="cbbda-129">İçinde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], veri modelini gösteren .edmx dosyasının açın.</span><span class="sxs-lookup"><span data-stu-id="cbbda-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="cbbda-130">İçinde **modeli tarayıcısı**, model sağ tıklayın, **özellikleri**, varlık kapsayıcısının adı not edin.</span><span class="sxs-lookup"><span data-stu-id="cbbda-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="cbbda-131">İçinde **Çözüm Gezgini**, adına sağ tıklayın, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proje ve ardından **Yeni Öğe Ekle**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="cbbda-132">İçinde **Yeni Öğe Ekle** iletişim kutusunda **WCF veri hizmeti**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="cbbda-133">Hizmet için bir ad sağlayın ve ardından **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="cbbda-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="cbbda-134">Yeni hizmet için XML biçimlendirme ve kodun dosyaları oluşturur.</span><span class="sxs-lookup"><span data-stu-id="cbbda-134"> creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="cbbda-135">Varsayılan olarak Kod Düzenleyicisi penceresini açar.</span><span class="sxs-lookup"><span data-stu-id="cbbda-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="cbbda-136">Veri Hizmeti kodunu açıklamayı değiştirin `/* TODO: put your data source class name here */` devraldığı türü ile veri hizmeti tanımlayan sınıf tanımında <xref:System.Data.Objects.ObjectContext> sınıfı ve bu, 2. adımda not veri modelinin varlık kapsayıcısı.</span><span class="sxs-lookup"><span data-stu-id="cbbda-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="cbbda-137">Veri Hizmeti kodunu veri çıkarır hizmeti varlık kümeleri erişmek yetkili istemcilerin etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="cbbda-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="cbbda-138">Daha fazla bilgi için bkz: [veri hizmeti oluşturma](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="cbbda-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="cbbda-139">Northwind.svc veri hizmeti bir Web tarayıcısı kullanarak test etmek için konudaki yönergeleri [bir Web tarayıcısından hizmete erişim](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="cbbda-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbda-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cbbda-140">See Also</span></span>  
 [<span data-ttu-id="cbbda-141">WCF veri hizmetleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="cbbda-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="cbbda-142">Veri Hizmetleri sağlayıcıları</span><span class="sxs-lookup"><span data-stu-id="cbbda-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="cbbda-143">Nasıl yapılır: yansıma sağlayıcısını kullanarak bir veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="cbbda-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="cbbda-144">Nasıl yapılır: SQL veri kaynağı için bir LINQ kullanarak bir veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="cbbda-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)