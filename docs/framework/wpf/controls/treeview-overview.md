---
title: "TreeView Genel Bakışı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bf50346cc179a5aae860a7651d28e104bac3c2ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="treeview-overview"></a><span data-ttu-id="da27b-102">TreeView Genel Bakışı</span><span class="sxs-lookup"><span data-stu-id="da27b-102">TreeView Overview</span></span>
<span data-ttu-id="da27b-103"><xref:System.Windows.Controls.TreeView> Denetimi daraltılabilir düğümleri kullanarak hiyerarşik yapıda bilgileri görüntülemek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="da27b-103">The <xref:System.Windows.Controls.TreeView> control provides a way to display information in a hierarchical structure by using collapsible nodes.</span></span> <span data-ttu-id="da27b-104">Bu konu tanıtır <xref:System.Windows.Controls.TreeView> ve <xref:System.Windows.Controls.TreeViewItem> denetler ve bunların kullanımıyla basit örnekler sağlar.</span><span class="sxs-lookup"><span data-stu-id="da27b-104">This topic introduces the <xref:System.Windows.Controls.TreeView> and <xref:System.Windows.Controls.TreeViewItem> controls, and provides simple examples of their use.</span></span>  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a><span data-ttu-id="da27b-105">TreeView nedir?</span><span class="sxs-lookup"><span data-stu-id="da27b-105">What Is a TreeView?</span></span>  
 <span data-ttu-id="da27b-106"><xref:System.Windows.Controls.TreeView>olan bir <xref:System.Windows.Controls.ItemsControl> öğeleri kullanarak katmandan <xref:System.Windows.Controls.TreeViewItem> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="da27b-106"><xref:System.Windows.Controls.TreeView> is an <xref:System.Windows.Controls.ItemsControl> that nests the items by using <xref:System.Windows.Controls.TreeViewItem> controls.</span></span> <span data-ttu-id="da27b-107">Aşağıdaki örnekte bir <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="da27b-107">The following example creates a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a><span data-ttu-id="da27b-108">TreeView oluşturma</span><span class="sxs-lookup"><span data-stu-id="da27b-108">Creating a TreeView</span></span>  
 <span data-ttu-id="da27b-109"><xref:System.Windows.Controls.TreeView> Denetimi içeren bir hiyerarşiye <xref:System.Windows.Controls.TreeViewItem> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="da27b-109">The <xref:System.Windows.Controls.TreeView> control contains a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls.</span></span> <span data-ttu-id="da27b-110">A <xref:System.Windows.Controls.TreeViewItem> denetimi bir <xref:System.Windows.Controls.HeaderedItemsControl> olan bir <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> ve bir <xref:System.Windows.Controls.ItemsControl.Items%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="da27b-110">A <xref:System.Windows.Controls.TreeViewItem> control is a <xref:System.Windows.Controls.HeaderedItemsControl> that has a <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> and an <xref:System.Windows.Controls.ItemsControl.Items%2A> collection.</span></span>  
  
 <span data-ttu-id="da27b-111">Tanımlıyorsanız, bir <xref:System.Windows.Controls.TreeView> kullanarak [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], açıkça tanımlayabilirsiniz <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> içeriğini bir <xref:System.Windows.Controls.TreeViewItem> denetim ve koleksiyonu oluşturan öğeler.</span><span class="sxs-lookup"><span data-stu-id="da27b-111">If you are defining a <xref:System.Windows.Controls.TreeView> by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can explicitly define the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> content of a <xref:System.Windows.Controls.TreeViewItem> control and the items that make up its collection.</span></span> <span data-ttu-id="da27b-112">Önceki çizimde, bu yöntem gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="da27b-112">The previous illustration demonstrates this method.</span></span>  
  
 <span data-ttu-id="da27b-113">Ayrıca belirtebilirsiniz bir <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> bir veri kaynağı ve ardından belirtin bir <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> ve <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> tanımlamak için <xref:System.Windows.Controls.TreeViewItem> içeriği.</span><span class="sxs-lookup"><span data-stu-id="da27b-113">You can also specify an <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> as a data source and then specify a <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> and <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> to define the <xref:System.Windows.Controls.TreeViewItem> content.</span></span>  
  
 <span data-ttu-id="da27b-114">Düzenini tanımlamak için bir <xref:System.Windows.Controls.TreeViewItem> denetimi de kullanabilirsiniz <xref:System.Windows.HierarchicalDataTemplate> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="da27b-114">To define the layout of a <xref:System.Windows.Controls.TreeViewItem> control, you can also use <xref:System.Windows.HierarchicalDataTemplate> objects.</span></span> <span data-ttu-id="da27b-115">Daha fazla bilgi ve bir örnek için bkz: [kullanım SelectedValue, SelectedValuePath ve SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).</span><span class="sxs-lookup"><span data-stu-id="da27b-115">For more information and an example, see [Use SelectedValue, SelectedValuePath, and SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).</span></span>  
  
 <span data-ttu-id="da27b-116">Bir öğe değilse, bir <xref:System.Windows.Controls.TreeViewItem> denetimi, bunu otomatik olarak içine alınır tarafından bir <xref:System.Windows.Controls.TreeViewItem> denetimi <xref:System.Windows.Controls.TreeView> denetim görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="da27b-116">If an item is not a <xref:System.Windows.Controls.TreeViewItem> control, it is automatically enclosed by a <xref:System.Windows.Controls.TreeViewItem> control when the <xref:System.Windows.Controls.TreeView> control is displayed.</span></span>  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a><span data-ttu-id="da27b-117">Genişletme ve daraltma TreeViewItem</span><span class="sxs-lookup"><span data-stu-id="da27b-117">Expanding and Collapsing a TreeViewItem</span></span>  
 <span data-ttu-id="da27b-118">Kullanıcı genişletir, bir <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> özelliği ayarlanmış `true`.</span><span class="sxs-lookup"><span data-stu-id="da27b-118">If the user expands a <xref:System.Windows.Controls.TreeViewItem>, the <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> property is set to `true`.</span></span> <span data-ttu-id="da27b-119">Ayrıca genişletebilir veya daraltabilirsiniz bir <xref:System.Windows.Controls.TreeViewItem> ayarlayarak doğrudan kullanıcı eylemi olmadan <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> özelliğine `true` (expand) veya `false` (daraltma).</span><span class="sxs-lookup"><span data-stu-id="da27b-119">You can also expand or collapse a <xref:System.Windows.Controls.TreeViewItem> without any direct user action by setting the <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> property to `true` (expand) or `false` (collapse).</span></span> <span data-ttu-id="da27b-120">Bu özellik değiştiğinde bir <xref:System.Windows.Controls.TreeViewItem.Expanded> veya <xref:System.Windows.Controls.TreeViewItem.Collapsed> olayı oluşur.</span><span class="sxs-lookup"><span data-stu-id="da27b-120">When this property changes, an <xref:System.Windows.Controls.TreeViewItem.Expanded> or <xref:System.Windows.Controls.TreeViewItem.Collapsed> event occurs.</span></span>  
  
 <span data-ttu-id="da27b-121">Zaman <xref:System.Windows.FrameworkElement.BringIntoView%2A> yöntemi çağrıldığında bir <xref:System.Windows.Controls.TreeViewItem> denetimi <xref:System.Windows.Controls.TreeViewItem> ve kendi üst <xref:System.Windows.Controls.TreeViewItem> denetimleri genişletin.</span><span class="sxs-lookup"><span data-stu-id="da27b-121">When the <xref:System.Windows.FrameworkElement.BringIntoView%2A> method is called on a <xref:System.Windows.Controls.TreeViewItem> control, the <xref:System.Windows.Controls.TreeViewItem> and its parent <xref:System.Windows.Controls.TreeViewItem> controls expand.</span></span> <span data-ttu-id="da27b-122">Varsa bir <xref:System.Windows.Controls.TreeViewItem> görünür veya kısmen görünür değil <xref:System.Windows.Controls.TreeView> görünür yapmak için kayar.</span><span class="sxs-lookup"><span data-stu-id="da27b-122">If a <xref:System.Windows.Controls.TreeViewItem> is not visible or partially visible, the <xref:System.Windows.Controls.TreeView> scrolls to make it visible.</span></span>  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a><span data-ttu-id="da27b-123">TreeViewItem seçimi</span><span class="sxs-lookup"><span data-stu-id="da27b-123">TreeViewItem Selection</span></span>  
 <span data-ttu-id="da27b-124">Bir kullanıcı tıkladığında bir <xref:System.Windows.Controls.TreeViewItem> , seçmek için Denetim <xref:System.Windows.Controls.TreeViewItem.Selected> olayı oluşur ve kendi <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> özelliği ayarlanmış `true`.</span><span class="sxs-lookup"><span data-stu-id="da27b-124">When a user clicks a <xref:System.Windows.Controls.TreeViewItem> control to select it, the <xref:System.Windows.Controls.TreeViewItem.Selected> event occurs, and its <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> property is set to `true`.</span></span> <span data-ttu-id="da27b-125"><xref:System.Windows.Controls.TreeViewItem> Haline <xref:System.Windows.Controls.TreeView.SelectedItem%2A> , <xref:System.Windows.Controls.TreeView> denetim.</span><span class="sxs-lookup"><span data-stu-id="da27b-125">The <xref:System.Windows.Controls.TreeViewItem> also becomes the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of the <xref:System.Windows.Controls.TreeView> control.</span></span> <span data-ttu-id="da27b-126">Buna karşılık, seçim değiştiğinde alanından bir <xref:System.Windows.Controls.TreeViewItem> denetim, kendi <xref:System.Windows.Controls.TreeViewItem.Unselected> olayı oluşur ve kendi <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> özelliği ayarlanmış `false`.</span><span class="sxs-lookup"><span data-stu-id="da27b-126">Conversely, when the selection changes from a <xref:System.Windows.Controls.TreeViewItem> control, its <xref:System.Windows.Controls.TreeViewItem.Unselected> event occurs and its <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> property is set to `false`.</span></span>  
  
 <span data-ttu-id="da27b-127"><xref:System.Windows.Controls.TreeView.SelectedItem%2A> Özellikte <xref:System.Windows.Controls.TreeView> denetim özelliği salt okunur; bu nedenle, açıkça bunu göremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="da27b-127">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property on the <xref:System.Windows.Controls.TreeView> control is a read-only property; hence, you cannot explicitly set it.</span></span> <span data-ttu-id="da27b-128"><xref:System.Windows.Controls.TreeView.SelectedItem%2A> Özellik ayarlanmışsa üzerinde kullanıcı bir <xref:System.Windows.Controls.TreeViewItem> denetim veya ne zaman <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> özelliği ayarlanmış `true` üzerinde <xref:System.Windows.Controls.TreeViewItem> denetim.</span><span class="sxs-lookup"><span data-stu-id="da27b-128">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property is set if the user clicks on a <xref:System.Windows.Controls.TreeViewItem> control or when the <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> property is set to `true` on the <xref:System.Windows.Controls.TreeViewItem> control.</span></span>  
  
 <span data-ttu-id="da27b-129">Kullanım <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> özelliği belirtmek için bir <xref:System.Windows.Controls.TreeView.SelectedValue%2A> , bir <xref:System.Windows.Controls.TreeView.SelectedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="da27b-129">Use the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> of a <xref:System.Windows.Controls.TreeView.SelectedItem%2A>.</span></span> <span data-ttu-id="da27b-130">Daha fazla bilgi için bkz: [kullanım SelectedValue, SelectedValuePath ve SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).</span><span class="sxs-lookup"><span data-stu-id="da27b-130">For more information, see [Use SelectedValue, SelectedValuePath, and SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).</span></span>  
  
 <span data-ttu-id="da27b-131">Üzerinde bir olay işleyicisi kaydedebilirsiniz <xref:System.Windows.Controls.TreeView.SelectedItemChanged> seçili belirlemek için olay <xref:System.Windows.Controls.TreeViewItem> değişiklikler.</span><span class="sxs-lookup"><span data-stu-id="da27b-131">You can register an event handler on the <xref:System.Windows.Controls.TreeView.SelectedItemChanged> event in order to determine when a selected <xref:System.Windows.Controls.TreeViewItem> changes.</span></span> <span data-ttu-id="da27b-132"><xref:System.Windows.RoutedPropertyChangedEventArgs%601> Olay işleyicisi belirtir sağlanan olan <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, önceki seçimi olduğu ve <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, geçerli seçim olduğu.</span><span class="sxs-lookup"><span data-stu-id="da27b-132">The <xref:System.Windows.RoutedPropertyChangedEventArgs%601> that is provided to the event handler specifies the <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, which is the previous selection, and the <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, which is the current selection.</span></span> <span data-ttu-id="da27b-133">Her iki değer `null` uygulama veya kullanıcıya önceki ya da geçerli bir seçim değil yapmadığında.</span><span class="sxs-lookup"><span data-stu-id="da27b-133">Either value can be `null` if the application or user has not made a previous or current selection.</span></span>  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a><span data-ttu-id="da27b-134">TreeView Stili</span><span class="sxs-lookup"><span data-stu-id="da27b-134">TreeView Style</span></span>  
 <span data-ttu-id="da27b-135">Varsayılan stilini bir <xref:System.Windows.Controls.TreeView> denetim yerleştirir içinde bir <xref:System.Windows.Controls.StackPanel> içeren nesne bir <xref:System.Windows.Controls.ScrollViewer> denetim.</span><span class="sxs-lookup"><span data-stu-id="da27b-135">The default style for a <xref:System.Windows.Controls.TreeView> control places it inside a <xref:System.Windows.Controls.StackPanel> object that contains a <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="da27b-136">Ayarladığınızda <xref:System.Windows.FrameworkElement.Width%2A> ve <xref:System.Windows.FrameworkElement.Height%2A> özelliklerini bir <xref:System.Windows.Controls.TreeView>, bu değerleri boyutuna kullanılan <xref:System.Windows.Controls.StackPanel> görüntüler nesne <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="da27b-136">When you set the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties for a <xref:System.Windows.Controls.TreeView>, these values are used to size the <xref:System.Windows.Controls.StackPanel> object that displays the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="da27b-137">Görüntülenecek içerik görüntü alanından daha büyükse bir <xref:System.Windows.Controls.ScrollViewer> kullanıcı kaydırmak otomatik olarak görüntüler, böylece <xref:System.Windows.Controls.TreeView> içeriği.</span><span class="sxs-lookup"><span data-stu-id="da27b-137">If the content to display is larger than the display area, a <xref:System.Windows.Controls.ScrollViewer> automatically displays so that the user can scroll through the <xref:System.Windows.Controls.TreeView> content.</span></span>  
  
 <span data-ttu-id="da27b-138">Görünümünü özelleştirmek için bir <xref:System.Windows.Controls.TreeViewItem> denetlemek, Ayarla <xref:System.Windows.FrameworkElement.Style%2A> özelliğini özel <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="da27b-138">To customize the appearance of a <xref:System.Windows.Controls.TreeViewItem> control, set the <xref:System.Windows.FrameworkElement.Style%2A> property to a custom <xref:System.Windows.Style>.</span></span>  
  
 <span data-ttu-id="da27b-139">Aşağıdaki örnekte nasıl ayarlanacağını gösterir <xref:System.Windows.Controls.Control.Foreground%2A> ve <xref:System.Windows.Controls.Control.FontSize%2A> özellik değerleri için bir <xref:System.Windows.Controls.TreeViewItem> kullanarak denetim bir <xref:System.Windows.FrameworkElement.Style%2A>.</span><span class="sxs-lookup"><span data-stu-id="da27b-139">The following example shows how to set the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.FontSize%2A> property values for a <xref:System.Windows.Controls.TreeViewItem> control by using a <xref:System.Windows.FrameworkElement.Style%2A>.</span></span>  
  
 [!code-xaml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a><span data-ttu-id="da27b-140">Resimleri ve diğer içeriği TreeView öğeler ekleme</span><span class="sxs-lookup"><span data-stu-id="da27b-140">Adding Images and Other Content to TreeView Items</span></span>  
 <span data-ttu-id="da27b-141">Birden fazla nesne içerebilir <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> içeriğini bir <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="da27b-141">You can include more than one object in the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> content of a <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="da27b-142">Birden çok nesnenin içerecek şekilde <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> içerik, nesneleri bir düzen denetimi içine aşağıdaki gibi alın bir <xref:System.Windows.Controls.Panel> veya <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="da27b-142">To include multiple objects in <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> content, enclose the objects inside a layout control, such as a <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="da27b-143">Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> , bir <xref:System.Windows.Controls.TreeViewItem> olarak bir <xref:System.Windows.Controls.CheckBox> ve <xref:System.Windows.Controls.TextBlock> hem de iliştirilir bir <xref:System.Windows.Controls.DockPanel> denetim.</span><span class="sxs-lookup"><span data-stu-id="da27b-143">The following example shows how to define the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> of a <xref:System.Windows.Controls.TreeViewItem> as a <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.TextBlock> that are both enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span>  
  
 [!code-xaml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 <span data-ttu-id="da27b-144">Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.DataTemplate> içeren bir <xref:System.Windows.Controls.Image> ve <xref:System.Windows.Controls.TextBlock> içinde çevrelenmiş bir <xref:System.Windows.Controls.DockPanel> denetim.</span><span class="sxs-lookup"><span data-stu-id="da27b-144">The following example shows how to define a <xref:System.Windows.DataTemplate> that contains an <xref:System.Windows.Controls.Image> and a <xref:System.Windows.Controls.TextBlock> that are enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span> <span data-ttu-id="da27b-145">Kullanabileceğiniz bir <xref:System.Windows.DataTemplate> ayarlamak için <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> veya <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> için bir <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="da27b-145">You can use a <xref:System.Windows.DataTemplate> to set the <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> or <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> for a <xref:System.Windows.Controls.TreeViewItem>.</span></span>  
  
 [!code-xaml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="da27b-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="da27b-146">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="da27b-147">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="da27b-147">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)  
 [<span data-ttu-id="da27b-148">WPF içerik modeli</span><span class="sxs-lookup"><span data-stu-id="da27b-148">WPF Content Model</span></span>](../../../../docs/framework/wpf/controls/wpf-content-model.md)