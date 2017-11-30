---
title: "Nasıl yapılır: Düz Renk ile bir Alanı Boyama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde7f7df5089806ffb3235393eacc855d137ee51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="5170f-102">Nasıl yapılır: Düz Renk ile bir Alanı Boyama</span><span class="sxs-lookup"><span data-stu-id="5170f-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="5170f-103">Düz renk ile alanı boyamak için önceden tanımlanmış sistem fırçası gibi kullanabilir <xref:System.Windows.Media.Brushes.Red%2A> veya <xref:System.Windows.Media.Brushes.Blue%2A>, ya da yeni bir oluşturabilirsiniz <xref:System.Windows.Media.SolidColorBrush> tanımlamak ve kendi <xref:System.Windows.Media.SolidColorBrush.Color%2A> alfa, kırmızı, yeşil ve mavi değerleri kullanarak.</span><span class="sxs-lookup"><span data-stu-id="5170f-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="5170f-104">XAML'de, onaltılık gösterimde kullanarak da bir alanı düz renk ile Boyama.</span><span class="sxs-lookup"><span data-stu-id="5170f-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="5170f-105">Aşağıdaki örnekler boyamak için her bu teknikleri kullanan bir <xref:System.Windows.Shapes.Rectangle> mavi.</span><span class="sxs-lookup"><span data-stu-id="5170f-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5170f-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="5170f-106">Example</span></span>  
 <span data-ttu-id="5170f-107">**Önceden tanımlanmış fırça kullanma**</span><span class="sxs-lookup"><span data-stu-id="5170f-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="5170f-108">Aşağıdaki örnekte önceden tanımlanmış fırça kullanır <xref:System.Windows.Media.Brushes.Blue%2A> dikdörtgen mavi boyamak için.</span><span class="sxs-lookup"><span data-stu-id="5170f-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="5170f-109">**Onaltılık gösterim kullanılarak**</span><span class="sxs-lookup"><span data-stu-id="5170f-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="5170f-110">Sonraki örnek 8 basamaklı onaltılık gösterim dikdörtgen mavi boyamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="5170f-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="5170f-111">**ARGB değerleri kullanma**</span><span class="sxs-lookup"><span data-stu-id="5170f-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="5170f-112">Sonraki örnekte bir <xref:System.Windows.Media.SolidColorBrush> ve açıklar kendi <xref:System.Windows.Media.SolidColorBrush.Color%2A> değerlerini mavi renk için ARGB kullanarak.</span><span class="sxs-lookup"><span data-stu-id="5170f-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="5170f-113">Renk açıklayan diğer yolları için bkz: <xref:System.Windows.Media.Color> yapısı.</span><span class="sxs-lookup"><span data-stu-id="5170f-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="5170f-114">**İlgili Konular**</span><span class="sxs-lookup"><span data-stu-id="5170f-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="5170f-115">Hakkında daha fazla bilgi için <xref:System.Windows.Media.SolidColorBrush> ve ek örnekler için bkz: [gradyan genel bakış ve düz renk ile Boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="5170f-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="5170f-116">Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır <xref:System.Windows.Media.SolidColorBrush> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="5170f-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="5170f-117">Tam bir örnek için bkz: [Fırçalar örnek](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="5170f-117">For the complete sample, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5170f-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5170f-118">See Also</span></span>  
 <xref:System.Windows.Media.Brushes>