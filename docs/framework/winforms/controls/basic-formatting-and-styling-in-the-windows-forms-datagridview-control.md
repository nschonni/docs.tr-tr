---
title: "Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c6ae9c4159f8f9eafd73608e4fc3f4a646c1eaa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d5bef-102">Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller</span><span class="sxs-lookup"><span data-stu-id="d5bef-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d5bef-103">`DataGridView` Denetim temel hücrelerin görünüşünü ve görüntüyü biçimlendirme hücre değerleri tanımlamak kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="d5bef-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="d5bef-104">Görünüm tanımlayabilir ve biçimlendirme stilleri tek tek hücreler, belirli sütunları ve satırları hücrelerde veya denetimdeki tüm hücreleri özelliklerini ayarlayarak `DataGridViewCellStyle` çeşitli erişilen nesneler `DataGridView` denetleyen özellikler.</span><span class="sxs-lookup"><span data-stu-id="d5bef-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="d5bef-105">Ayrıca, dinamik olarak hücre değeri gibi etkenlere işleyerek göre bu stiller değiştirebileceğiniz `CellFormatting` olay.</span><span class="sxs-lookup"><span data-stu-id="d5bef-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5bef-106">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="d5bef-106">In This Section</span></span>  
 [<span data-ttu-id="d5bef-107">Nasıl yapılır: kenarlığı değiştirmek ve kılavuz çizgisi stilleri Windows Forms DataGridView denetiminde</span><span class="sxs-lookup"><span data-stu-id="d5bef-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="d5bef-108">Nasıl ayarlanacağını açıklar `DataGridView` denetim sınır ve sınır satırları hücreler arasında görünümünü tanımlayan özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d5bef-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="d5bef-109">Windows Forms DataGridView denetimindeki hücre stilleri</span><span class="sxs-lookup"><span data-stu-id="d5bef-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-110">Açıklar `DataGridViewCellStyle` sınıfı ve bu tür özellikleri denetiminde hücrelerin nasıl görüntüleneceğini tanımlamak için nasıl etkileşim kurduklarını.</span><span class="sxs-lookup"><span data-stu-id="d5bef-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="d5bef-111">Nasıl yapılır: Windows Forms DataGridView denetimi için varsayılan hücre stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="d5bef-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-112">Nasıl kullanılacağını açıklar `DataGridViewCellStyle` belirli satırları ve sütunları ve tüm denetiminde hücreler varsayılan görünümünü tanımlamak için özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d5bef-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="d5bef-113">Nasıl yapılır: biçim verileri Windows Forms DataGridView denetiminde</span><span class="sxs-lookup"><span data-stu-id="d5bef-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-114">Kullanarak hücre görüntüleme değerlerinin nasıl biçimlendirileceğini tanımlar `DataGridViewCellStyle` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d5bef-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="d5bef-115">Nasıl yapılır: Windows Forms DataGridView denetiminde yazı tipi ve renk stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="d5bef-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-116">Nasıl kullanılacağını açıklar `DefaultCellStyle` temel ayarlamak için özellik denetiminde tüm hücreleri için özellikleri görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="d5bef-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="d5bef-117">Nasıl yapılır: Windows Forms DataGridView denetimi için alternatif satır stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="d5bef-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-118">Büyük defter benzeri etkisi farklı görüntülenen değişen satırların kullanarak denetiminde oluşturmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="d5bef-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="d5bef-119">Nasıl yapılır: Windows Forms DataGridView denetimindeki satırları özelleştirmek için satır şablonunu kullanma</span><span class="sxs-lookup"><span data-stu-id="d5bef-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="d5bef-120">Nasıl kullanılacağını açıklar `RowTemplate` denetimdeki tüm satırlar için kullanılacak satır özelliklerini ayarlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="d5bef-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5bef-121">Başvuru</span><span class="sxs-lookup"><span data-stu-id="d5bef-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d5bef-122">Başvuru belgelerine sağlar <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="d5bef-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="d5bef-123">Başvuru belgelerine sağlar <xref:System.Windows.Forms.DataGridViewCellStyle> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d5bef-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="d5bef-124">Başvuru belgelerine sağlar <xref:System.Windows.Forms.DataGridView.CellFormatting> olay.</span><span class="sxs-lookup"><span data-stu-id="d5bef-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="d5bef-125">Başvuru belgelerine sağlar <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d5bef-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5bef-126">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="d5bef-126">Related Sections</span></span>  
 [<span data-ttu-id="d5bef-127">Windows Forms DataGridView denetimini özelleştirme</span><span class="sxs-lookup"><span data-stu-id="d5bef-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5bef-128">Özel boyama açıklayan konulara sağlar <xref:System.Windows.Forms.DataGridView> hücre ve satırları ve oluşturma türetilmiş hücre, sütun ve satır türleri.</span><span class="sxs-lookup"><span data-stu-id="d5bef-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="d5bef-129">Temel sütun, satır ve hücre özellikleri Windows Forms DataGridView denetiminde</span><span class="sxs-lookup"><span data-stu-id="d5bef-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="d5bef-130">Yaygın olarak açıklayan konulara hücre, satır ve sütun özelliklerinin kullanılmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="d5bef-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bef-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d5bef-131">See Also</span></span>  
 [<span data-ttu-id="d5bef-132">DataGridView denetimi</span><span class="sxs-lookup"><span data-stu-id="d5bef-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)