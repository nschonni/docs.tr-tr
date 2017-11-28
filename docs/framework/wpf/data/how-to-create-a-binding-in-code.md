---
title: "Nasıl yapılır: Kod İçinde Bağlama Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6279de3b892d64bc48b4f67c9f08bd89dd1b7d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="1d2d2-102">Nasıl yapılır: Kod İçinde Bağlama Oluşturma</span><span class="sxs-lookup"><span data-stu-id="1d2d2-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="1d2d2-103">Bu örnek oluşturmak ve ayarlamak nasıl gösterir bir <xref:System.Windows.Data.Binding> kod.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d2d2-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="1d2d2-104">Example</span></span>  
 <span data-ttu-id="1d2d2-105"><xref:System.Windows.FrameworkElement> Sınıfı ve <xref:System.Windows.FrameworkContentElement> her ikisini kullanıma sınıfı bir `SetBinding` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="1d2d2-106">Bu sınıfların ya da devralan bir öğeyi bağlıyorsanız çağırabilirsiniz <xref:System.Windows.FrameworkElement.SetBinding%2A> doğrudan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="1d2d2-107">Aşağıdaki örnek, adlandırılmış bir sınıf oluşturur `MyData`, adında bir özellik içeren `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="1d2d2-108">Aşağıdaki örnek, bağlama kaynağı ayarlamak için bir bağlama nesnesinin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="1d2d2-109">Örnek kullanır <xref:System.Windows.FrameworkElement.SetBinding%2A> bağlamak için <xref:System.Windows.Controls.TextBlock.Text%2A> özelliği `myText`, olduğu bir <xref:System.Windows.Controls.TextBlock> denetlemek, çok `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="1d2d2-110">Tam kod örneği için bkz: [yalnızca kod bağlama örnek](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span><span class="sxs-lookup"><span data-stu-id="1d2d2-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="1d2d2-111">Çağırmak yerine <xref:System.Windows.FrameworkElement.SetBinding%2A>, kullanabileceğiniz <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statik yöntemi <xref:System.Windows.Data.BindingOperations> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="1d2d2-112">Aşağıdaki örnek, çağrıları <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> yerine <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> bağlamak için `myText` için `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="1d2d2-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1d2d2-113">See Also</span></span>  
 [<span data-ttu-id="1d2d2-114">Veri bağlama genel bakış</span><span class="sxs-lookup"><span data-stu-id="1d2d2-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="1d2d2-115">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="1d2d2-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)