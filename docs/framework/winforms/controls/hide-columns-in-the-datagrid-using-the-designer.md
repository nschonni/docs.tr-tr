---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimindeki Sütunları Gizleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6deefcfb4a1fcf0c1a3bd0d521e6a69ea6902dd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="95c67-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimindeki Sütunları Gizleme</span><span class="sxs-lookup"><span data-stu-id="95c67-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="95c67-103">Bazı durumlarda yalnızca bazı Windows Forms'ta kullanılabilir olan sütunları görüntülemek isteyeceksiniz <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="95c67-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="95c67-104">Örneğin, bir çalışan görüntülemek isteyebilirsiniz maaş sütun diğer kullanıcılardan gizleme sırasında yönetim kimlik bilgilerine sahip kullanıcılar için.</span><span class="sxs-lookup"><span data-stu-id="95c67-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="95c67-105">Alternatif olarak, yalnızca bazıları görüntülemek istediğiniz sayıda sütun içeren bir veri kaynağına denetimi bağlamak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="95c67-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="95c67-106">Bu durumda, genellikle görüntüleme yerine gizleyip ilgilenen olmayan sütunları kaldırır.</span><span class="sxs-lookup"><span data-stu-id="95c67-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="95c67-107">Daha fazla bilgi için bkz: [nasıl yapılır: ekleme ve kaldırma sütunları Windows Forms DataGridView denetimi kullanarak Tasarımcı](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="95c67-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="95c67-108">Aşağıdaki yordam gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="95c67-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="95c67-109">Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="95c67-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95c67-110">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="95c67-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="95c67-111">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="95c67-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="95c67-112">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="95c67-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="95c67-113">Tasarımcı kullanarak bir sütunu gizlemek için</span><span class="sxs-lookup"><span data-stu-id="95c67-113">To hide a column using the designer</span></span>  
  
1.  <span data-ttu-id="95c67-114">Akıllı etiket karakteri tıklayın (![akıllı etiket karakteri](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) sağ üst köşesindeki <xref:System.Windows.Forms.DataGridView> denetlemek ve ardından **Edit Columns**.</span><span class="sxs-lookup"><span data-stu-id="95c67-114">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="95c67-115">Bir sütun seçin **seçili sütun** listesi.</span><span class="sxs-lookup"><span data-stu-id="95c67-115">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="95c67-116">İçinde **sütun özellikleri** kılavuzunu, ayarlamak <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="95c67-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95c67-117">Bir sütun temizleyerek eklerken gizleyebilirsiniz **görünür** onay kutusuna **Sütun Ekle** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="95c67-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c67-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="95c67-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="95c67-119">Nasıl yapılır: ekleme ve kaldırma sütunları Windows Forms DataGridView denetiminde Tasarımcısı'nı kullanarak</span><span class="sxs-lookup"><span data-stu-id="95c67-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="95c67-120">Nasıl yapılır: bir Windows uygulaması projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="95c67-120">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="95c67-121">Nasıl yapılır: Windows formlarına denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="95c67-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)