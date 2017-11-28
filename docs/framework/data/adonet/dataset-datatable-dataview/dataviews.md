---
title: DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2653a94992440b747371c5d8a7b9daa66b3e3ab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="dataviews"></a><span data-ttu-id="c4966-102">DataView</span><span class="sxs-lookup"><span data-stu-id="c4966-102">DataViews</span></span>
<span data-ttu-id="c4966-103">A <xref:System.Data.DataView> depolanan verilerin farklı görünümlerini oluşturmanızı sağlayan bir <xref:System.Data.DataTable>, veri bağlama uygulamalarında sık kullanılan bir özellik.</span><span class="sxs-lookup"><span data-stu-id="c4966-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="c4966-104">Kullanarak bir **DataView**farklı sıralamalar olan bir tabloda veri getirebilir ve veri satırı durum ya da bir filtre ifadesi göre göre filtre uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4966-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="c4966-105">A **DataView** temel veri dinamik bir görünümünü sunan **DataTable**: Bunlar ortaya çıktığında içerik, sıralama ve üyelik değişiklikleri yansıtacak.</span><span class="sxs-lookup"><span data-stu-id="c4966-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="c4966-106">Bu davranış farklı **seçin** yöntemi **DataTable**, döndüren bir <xref:System.Data.DataRow> bir tablo diziden dayalı üzerinde belirli bir filtre ve/veya sıralama düzeni: thiscontent değişiklikleri yansıtır Tablo, ancak üyeliğini temel ve sıralama statik kalır.</span><span class="sxs-lookup"><span data-stu-id="c4966-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="c4966-107">Dinamik özelliklerini **DataView** veri bağlama uygulamaları için ideal olun.</span><span class="sxs-lookup"><span data-stu-id="c4966-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="c4966-108">A **DataView** için uygulayabileceğiniz farklı sıralama ve filtreleme ölçütlerini çok bir veritabanı görünüm gibi verileri tek bir dizi dinamik bir görünümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4966-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="c4966-109">Ancak, bir veritabanı görünümü aksine bir **DataView** tablo olarak kabul edilemiyor ve birleştirilmiş tablolar görünümünü sağlayamaz.</span><span class="sxs-lookup"><span data-stu-id="c4966-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="c4966-110">Ayrıca kaynak tablo mevcut sütunları dışlanamaz veya kaynak tabloda bulunmayan hesaplama sütunlar gibi sütunları ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4966-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="c4966-111">Kullanabileceğiniz bir <xref:System.Data.DataView.DataViewManager%2A> tüm tablolarda görünüm ayarlarını yönetmek için bir **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c4966-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="c4966-112">**DataViewManager** her tablo için varsayılan görünüm ayarlarını yönetmek için kolay bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4966-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="c4966-113">Bir denetim birden fazla tabloya bağlanırken bir **DataSet**, bağlayıcı için bir **DataViewManager** ideal bir seçimdir.</span><span class="sxs-lookup"><span data-stu-id="c4966-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4966-114">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="c4966-114">In This Section</span></span>  
 [<span data-ttu-id="c4966-115">DataView oluşturma</span><span class="sxs-lookup"><span data-stu-id="c4966-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="c4966-116">Nasıl oluşturulacağını açıklar bir **DataView** için bir **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c4966-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="c4966-117">Verileri sıralama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="c4966-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="c4966-118">Özelliklerini ayarlamak açıklar bir **DataView** veri satır kümelerine belirli filtre ölçütlere geri dönmek için veya belirli bir sıralama düzeni içinde verileri döndürmek için.</span><span class="sxs-lookup"><span data-stu-id="c4966-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="c4966-119">DataRow ve DataRowView</span><span class="sxs-lookup"><span data-stu-id="c4966-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="c4966-120">Tarafından sunulan veri erişim açıklar **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c4966-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="c4966-121">Satırları bulma</span><span class="sxs-lookup"><span data-stu-id="c4966-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="c4966-122">Belirli bir satır bulmak açıklar bir **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c4966-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="c4966-123">ChildViews ve ilişkileri</span><span class="sxs-lookup"><span data-stu-id="c4966-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="c4966-124">Veri görünümleri kullanarak bir üst-alt ilişkisi oluşturmayı açıklar bir **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c4966-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="c4966-125">DataView değiştirme</span><span class="sxs-lookup"><span data-stu-id="c4966-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="c4966-126">Temel veri değiştirmeyi açıklar **DataTable** aracılığıyla **DataView**etkinleştirerek veya devre dışı güncelleştirmeler dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="c4966-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="c4966-127">DataView olayları işleme</span><span class="sxs-lookup"><span data-stu-id="c4966-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="c4966-128">Nasıl kullanılacağını açıklar **ListChanged** bildirim almak için olay olduğunda içeriği veya sırasını bir **DataView** güncelleştiriliyor.</span><span class="sxs-lookup"><span data-stu-id="c4966-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="c4966-129">DataView yönetme</span><span class="sxs-lookup"><span data-stu-id="c4966-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="c4966-130">Nasıl kullanılacağını açıklar bir **DataViewManager** yönetmek için **DataView** ayarları her tablo için bir **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c4966-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c4966-131">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="c4966-131">Related Sections</span></span>  
 [<span data-ttu-id="c4966-132">ASP.NET Web uygulamaları</span><span class="sxs-lookup"><span data-stu-id="c4966-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/en-us/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="c4966-133">ASP.NET uygulamaları, Web formları ve Web hizmetleri oluşturmak için genel bakışlar ve ayrıntılı, adım adım yordamlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4966-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="c4966-134">Windows uygulamaları</span><span class="sxs-lookup"><span data-stu-id="c4966-134">Windows Applications</span></span>](http://msdn.microsoft.com/en-us/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="c4966-135">Windows Forms ve konsol uygulamaları ile çalışma hakkında ayrıntılı bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4966-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="c4966-136">Veri kümeleri, DataTable ve DataView</span><span class="sxs-lookup"><span data-stu-id="c4966-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="c4966-137">Açıklar **DataSet** nesne ve uygulama verilerini yönetmek için nasıl kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4966-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="c4966-138">DataTables</span><span class="sxs-lookup"><span data-stu-id="c4966-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="c4966-139">Açıklar **DataTable** nesne ve tek başına ya da bir parçası olarak uygulama verilerini yönetmek için nasıl kullanabileceğiniz bir **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c4966-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="c4966-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c4966-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="c4966-141">ADO.NET açıklar mimarisi ve bileşenleri ve ADO.NET mevcut veri kaynaklarına erişmek ve uygulama verilerini yönetmek için nasıl kullanılacağını.</span><span class="sxs-lookup"><span data-stu-id="c4966-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4966-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c4966-142">See Also</span></span>  
 [<span data-ttu-id="c4966-143">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="c4966-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)