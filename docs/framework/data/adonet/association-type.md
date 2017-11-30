---
title: "ilişki türü"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 476a92979ff0dc6292e64ce5514cc600a9dee50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="association-type"></a><span data-ttu-id="52c3e-102">ilişki türü</span><span class="sxs-lookup"><span data-stu-id="52c3e-102">association type</span></span>
<span data-ttu-id="52c3e-103">Bir *ilişkilendirme türü* (bir ilişki olarak da bilinir) ilişkileri varlık veri modeli (EDM) açıklamak için temel yapı bloğu.</span><span class="sxs-lookup"><span data-stu-id="52c3e-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="52c3e-104">Bir kavramsal modelde ilişkilendirme iki arasındaki bir ilişkiyi temsil eder. [varlık türleri](../../../../docs/framework/data/adonet/entity-type.md) (gibi `Customer` ve `Order`).</span><span class="sxs-lookup"><span data-stu-id="52c3e-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="52c3e-105">Bir uygulamada belirli bir ilişki ilişkilendirme örneğini temsil eder (bir örneği arasında bir ilişki gibi `Customer` bir örneği ile `Order`).</span><span class="sxs-lookup"><span data-stu-id="52c3e-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="52c3e-106">İlişkilendirme örnekleri mantıksal olarak gruplandırılmış bir [ilişkilendirme kümesi](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="52c3e-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="52c3e-107">Bir ilişkilendirme tanımı aşağıdaki bilgileri içerir:</span><span class="sxs-lookup"><span data-stu-id="52c3e-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="52c3e-108">Benzersiz bir ad.</span><span class="sxs-lookup"><span data-stu-id="52c3e-108">A unique name.</span></span> <span data-ttu-id="52c3e-109">(Gerekli)</span><span class="sxs-lookup"><span data-stu-id="52c3e-109">(Required)</span></span>  
  
-   <span data-ttu-id="52c3e-110">İki [ilişki uçları](../../../../docs/framework/data/adonet/association-end.md), ilişkiyi her bir varlık türü için bir tane.</span><span class="sxs-lookup"><span data-stu-id="52c3e-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="52c3e-111">(Gerekli)</span><span class="sxs-lookup"><span data-stu-id="52c3e-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c3e-112">Bir ilişkilendirme ikiden fazla varlık türleri arasındaki ilişkiyi temsil edilemez.</span><span class="sxs-lookup"><span data-stu-id="52c3e-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="52c3e-113">Bir ilişkilendirme ancak, kendi kendine ilişki her ilişki uçlarından biri için aynı varlık türü belirterek tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="52c3e-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="52c3e-114">A [başvuru bütünlüğü kısıtlaması](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="52c3e-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="52c3e-115">(İsteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="52c3e-115">(Optional)</span></span>  
  
 <span data-ttu-id="52c3e-116">Her ilişki ucu belirtmelisiniz bir [ilişkilendirme son Çokluk](../../../../docs/framework/data/adonet/association-end-multiplicity.md) bir ilişki sonunda olabilir varlık türü örneklerinin sayısını belirtir.</span><span class="sxs-lookup"><span data-stu-id="52c3e-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="52c3e-117">Bir ilişkilendirme end Çokluk bir değer (0.. 1 çokluğa) bir (1), sıfır veya bir veya birçok (*) olabilir.</span><span class="sxs-lookup"><span data-stu-id="52c3e-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span> <span data-ttu-id="52c3e-118">Varlık türü örnekleri ilişkinin bir ucundaki üzerinden erişilebilir [Gezinti özellikleri](../../../../docs/framework/data/adonet/navigation-property.md) veya bir varlık türü gösteriliyorsa yabancı anahtarlar.</span><span class="sxs-lookup"><span data-stu-id="52c3e-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="52c3e-119">Daha fazla bilgi için bkz: [varlık veri modeli: yabancı anahtarlar](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="52c3e-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c3e-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="52c3e-120">Example</span></span>  
 <span data-ttu-id="52c3e-121">Aşağıdaki diyagramda iki ilişkilendirmeleri kavramsal modelle gösterir: `PublishedBy` ve `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="52c3e-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="52c3e-122">İlişkilendirme sona `PublishedBy` ilişkisi olan `Book` ve `Publisher` varlık türleri.</span><span class="sxs-lookup"><span data-stu-id="52c3e-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="52c3e-123">Çokluğu `Publisher` sonudur bir (1) ve çokluğu `Book` sonudur birçok (*), bir yayımcı birçok books yayımlar ve kitap bir yayımcı tarafından yayımlanan gösteren.</span><span class="sxs-lookup"><span data-stu-id="52c3e-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="52c3e-124">![Örnek modeli](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="52c3e-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="52c3e-125">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) kavramsal şema tanım dili adlı bir etki alanına özgü dil (DSL) kullanır ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) kavramsal modeller tanımlamak için.</span><span class="sxs-lookup"><span data-stu-id="52c3e-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="52c3e-126">Aşağıdaki CSDL tanımlar `PublishedBy` Yukarıdaki diyagramda gösterildiği ilişkilendirme:</span><span class="sxs-lookup"><span data-stu-id="52c3e-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="52c3e-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="52c3e-127">See Also</span></span>  
 [<span data-ttu-id="52c3e-128">Varlık veri modeli temel kavramları</span><span class="sxs-lookup"><span data-stu-id="52c3e-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="52c3e-129">Varlık veri modeli</span><span class="sxs-lookup"><span data-stu-id="52c3e-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)