---
title: "Veri tanımlama dili ile çalışma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d65fb17796339f38be59b64e550d7ec77336083d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="65200-102">Veri tanımlama dili ile çalışma</span><span class="sxs-lookup"><span data-stu-id="65200-102">Working with Data Definition Language</span></span>
<span data-ttu-id="65200-103">İle başlayarak [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] sürüm 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] veri tanımlama dili (DDL) destekler.</span><span class="sxs-lookup"><span data-stu-id="65200-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="65200-104">Bu, oluşturmak veya bağlantı dizesi ve depolama (SSDL) model meta verileri temel alan bir veritabanı örneği silmek sağlar.</span><span class="sxs-lookup"><span data-stu-id="65200-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="65200-105">Aşağıdaki yöntemlerden <xref:System.Data.Objects.ObjectContext> aşağıdakileri gerçekleştirmek için bağlantı dizesini ve SSDL içeriği kullanın: oluşturmak veya veritabanını silin, veritabanı var ve oluşturulan DDL komut görüntülemek olup olmadığını denetleyin:</span><span class="sxs-lookup"><span data-stu-id="65200-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="65200-106">DDL komutları yürütülürken yeterli izinlere varsayar.</span><span class="sxs-lookup"><span data-stu-id="65200-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="65200-107">Daha önce listelenen yöntemleri işlerin çoğunu alttaki ADO.NET veri sağlayıcı için temsilci.</span><span class="sxs-lookup"><span data-stu-id="65200-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="65200-108">Veritabanı nesneleri oluşturmak için kullanılan adlandırma kuralı sorgulamak için kullanılan kuralları ile tutarlı olduğundan emin olmak için sağlayıcının sorumluluğundadır ve güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="65200-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="65200-109">Aşağıdaki örnek varolan modelini temel alan veritabanı oluşturmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="65200-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="65200-110">Ayrıca nesne bağlamı için yeni bir varlık nesnesi ekler ve veritabanına kaydeder.</span><span class="sxs-lookup"><span data-stu-id="65200-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="65200-111">Yordamlar</span><span class="sxs-lookup"><span data-stu-id="65200-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="65200-112">Varolan modelini temel alan bir veritabanı tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="65200-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="65200-113">Bir konsol uygulaması oluşturun.</span><span class="sxs-lookup"><span data-stu-id="65200-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="65200-114">Var olan bir model uygulamanıza ekleyin.</span><span class="sxs-lookup"><span data-stu-id="65200-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="65200-115">Adlı boş bir model eklemek `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="65200-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="65200-116">Boş bir model oluşturmak için bkz: [nasıl yapılır: yeni .edmx dosyasının oluşturma](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) konu.</span><span class="sxs-lookup"><span data-stu-id="65200-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="65200-117">SchoolModel.edmx dosyası projenize eklenir.</span><span class="sxs-lookup"><span data-stu-id="65200-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="65200-118">Kavramsal, depolama kopyalayın ve içerik Okul modeli eşleme [Okul modeli](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) konu.</span><span class="sxs-lookup"><span data-stu-id="65200-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="65200-119">SchoolModel.edmx dosyasını açın ve içeriği içinde `edmx:Runtime` etiketler.</span><span class="sxs-lookup"><span data-stu-id="65200-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="65200-120">Ana işlevinizi aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="65200-120">Add the following code to your main function.</span></span> <span data-ttu-id="65200-121">Kod DDL komut dosyası bir veritabanı oluşturur, yeni bir varlık bağlamına ekler ve değişiklikleri veritabanına kaydeder görünümleri, veritabanı sunucusu ile bağlantı dizesi başlatır.</span><span class="sxs-lookup"><span data-stu-id="65200-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]