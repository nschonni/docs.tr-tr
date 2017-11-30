---
title: "GDI+'da Açık ve Kapalı Eğriler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14da32848978299a0d0651596bbfbfe17c2e0d53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="6bbb5-102">GDI+'da Açık ve Kapalı Eğriler</span><span class="sxs-lookup"><span data-stu-id="6bbb5-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="6bbb5-103">İki eğri aşağıda gösterilmiştir: bir açık ve bir kapalı.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="6bbb5-104">![Açık ve kapalı Eğriler](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="6bbb5-104">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="6bbb5-105">Eğriler için yönetilen arabirimi</span><span class="sxs-lookup"><span data-stu-id="6bbb5-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="6bbb5-106">Kapalı Eğriler bir iç varsa ve bu nedenle fırça ile doldurulabilir.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="6bbb5-107"><xref:System.Drawing.Graphics> Sınıfını [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kapalı şekiller ve eğrilerle doldurmak için aşağıdaki yöntemleri sağlar: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, ve <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="6bbb5-108">Aşağıdaki yöntemlerden birini çağrısı zaman, belirli fırça türlerinden birini geçmesi gerekir (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, veya <xref:System.Drawing.Drawing2D.PathGradientBrush>) bağımsız değişken olarak.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="6bbb5-109"><xref:System.Drawing.Graphics.FillPie%2A> Bir yardımcı yöntemdir <xref:System.Drawing.Graphics.DrawArc%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="6bbb5-110">Gibi <xref:System.Drawing.Graphics.DrawArc%2A> yöntemi bir kısmı bir elips anahat çizer <xref:System.Drawing.Graphics.FillPie%2A> yöntemi elips iç kısmını doldurur.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="6bbb5-111">Aşağıdaki örnek, bir yay çizer ve karşılık gelen elipsin iç kısmını doldurur:</span><span class="sxs-lookup"><span data-stu-id="6bbb5-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="6bbb5-112">Yayı ve dolgulu pasta aşağıda gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="6bbb5-113">![Açık ve kapalı Eğriler](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="6bbb5-113">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="6bbb5-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A> Bir yardımcı yöntemdir <xref:System.Drawing.Graphics.DrawClosedCurve%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="6bbb5-115">Her iki yöntem için başlangıç noktası bitiş noktasına bağlanarak eğri otomatik olarak kapanır.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="6bbb5-116">Aşağıdaki örnek geçtiği bir eğri çizer (0, 0), (60, 20) ve (40, 50).</span><span class="sxs-lookup"><span data-stu-id="6bbb5-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="6bbb5-117">Ardından, bağlanarak otomatik olarak eğri kapatıldıktan (40, 50) (0, 0), başlangıç noktası için ve iç tam renkle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="6bbb5-118"><xref:System.Drawing.Graphics.FillPath%2A> Yöntemi bir yolu ayrı parçasını evin içindekiler doldurur.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="6bbb5-119">Bir yol parçasını kapalı eğri veya şekil, form değil, <xref:System.Drawing.Graphics.FillPath%2A> yöntemi otomatik olarak doldurma önce yolun parçasının kapatır.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="6bbb5-120">Aşağıdaki örnek, çizer ve yay, Kardinal eğri, bir dize ve bir pasta oluşan bir yol doldurur:</span><span class="sxs-lookup"><span data-stu-id="6bbb5-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="6bbb5-121">Aşağıdaki çizimde ile ve düz dolgu olmadan yolunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="6bbb5-122">Metin dizesindeki özetlenen, ancak, bunun doldurulmamış olduğunu Not <xref:System.Drawing.Graphics.DrawPath%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="6bbb5-123">Bu <xref:System.Drawing.Graphics.FillPath%2A> dizesindeki karakterlerin evin içindekiler boyar yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="6bbb5-124">![Bir yol dizesindeki](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="6bbb5-124">![String in a path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbb5-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6bbb5-125">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="6bbb5-126">Çizgiler, eğriler ve şekiller</span><span class="sxs-lookup"><span data-stu-id="6bbb5-126">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="6bbb5-127">Nasıl yapılır: çizim için grafik nesneleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="6bbb5-127">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="6bbb5-128">Yollar oluşturma ve çizme</span><span class="sxs-lookup"><span data-stu-id="6bbb5-128">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)