---
title: "Nasıl yapılır: çizim tek B &#233; zier eğri"
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="35ffc-102">Nasıl yapılır: çizim tek B &#233; zier eğri</span><span class="sxs-lookup"><span data-stu-id="35ffc-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="35ffc-103">Bir Bézier eğrisi dört noktaları tarafından tanımlanır: bir başlangıç noktası, iki denetim noktası ve bir uç nokta.</span><span class="sxs-lookup"><span data-stu-id="35ffc-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35ffc-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="35ffc-104">Example</span></span>  
 <span data-ttu-id="35ffc-105">Aşağıdaki örnek, başlangıç noktası (10, 100) ve (200, 100) uç noktası olan bir Bézier eğrisi çizer.</span><span class="sxs-lookup"><span data-stu-id="35ffc-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="35ffc-106">Denetim noktalarını olan (100, 10) ve (150 150).</span><span class="sxs-lookup"><span data-stu-id="35ffc-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="35ffc-107">Sonuçta elde edilen bir Bézier eğrisi başlangıç noktasını, denetim noktaları ve uç nokta ile birlikte aşağıda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="35ffc-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="35ffc-108">Çizimde de düz satırıyla dört noktası bağlanarak biçimlendirilmiş bir Çokgen eğri 's dışbükey hull gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="35ffc-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="35ffc-109">![Bezier eğrisi](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="35ffc-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35ffc-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="35ffc-110">Compiling the Code</span></span>  
 <span data-ttu-id="35ffc-111">Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="35ffc-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ffc-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35ffc-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="35ffc-113">GDI +'daki Bézier eğrileri</span><span class="sxs-lookup"><span data-stu-id="35ffc-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="35ffc-114">Nasıl yapılır: bir sıra Bézier eğrisi çizme</span><span class="sxs-lookup"><span data-stu-id="35ffc-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)