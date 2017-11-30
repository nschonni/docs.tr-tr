---
title: "&amp;= İşleci (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="bd6b8-102">&amp;= İşleci (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd6b8-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="bd6b8-103">Art arda ekler bir `String` ifade bir `String` değişken veya özellik ve değişken ya da özelliği için sonuç atar.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd6b8-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bd6b8-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="bd6b8-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="bd6b8-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="bd6b8-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-106">Required.</span></span> <span data-ttu-id="bd6b8-107">Tüm `String` değişken veya özellik.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="bd6b8-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-108">Required.</span></span> <span data-ttu-id="bd6b8-109">Tüm `String` ifade.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd6b8-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bd6b8-110">Remarks</span></span>  
 <span data-ttu-id="bd6b8-111">Öğe sol tarafındaki `&=` işleci basit bir skaler değişkeni, bir özellik veya bir dizi öğesi olabilir.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="bd6b8-112">Değişken veya özellik olamaz [salt okunur](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="bd6b8-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="bd6b8-113">`&=` İşleci art arda ekler `String` ifadesi, sağ taraftaki `String` değişkenin veya özelliğin, sol taraftaki ve değişken ya da kendi soldaki özelliğin sonucu atar.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="bd6b8-114">Aşırı Yükleme</span><span class="sxs-lookup"><span data-stu-id="bd6b8-114">Overloading</span></span>  
 <span data-ttu-id="bd6b8-115">[& İşleci](../../../visual-basic/language-reference/operators/concatenation-operator.md) olabilir *aşırı*, işleneni, sınıf veya yapı türüne sahip olduğunda bir sınıf veya yapı davranışını tanımlayabilirsiniz, anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bd6b8-116">Aşırı yükleme `&` işleci davranışını etkileyen `&=` işleci.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="bd6b8-117">Kodunuzu kullanıyorsa `&=` bir sınıf veya overloads yapısı `&`, yeniden tanımlanan davranışını anladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bd6b8-118">Daha fazla bilgi için bkz: [işleç yordamları](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bd6b8-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd6b8-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="bd6b8-119">Example</span></span>  
 <span data-ttu-id="bd6b8-120">Aşağıdaki örnek kullanır `&=` iki birleştirme işleci `String` değişkenleri ve ata ilk değişken sonucu.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd6b8-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bd6b8-121">See Also</span></span>  
 [<span data-ttu-id="bd6b8-122">& İşleci</span><span class="sxs-lookup"><span data-stu-id="bd6b8-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="bd6b8-123">+= İşleci</span><span class="sxs-lookup"><span data-stu-id="bd6b8-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="bd6b8-124">Atama İşleçleri</span><span class="sxs-lookup"><span data-stu-id="bd6b8-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="bd6b8-125">Birleştirme işleçleri</span><span class="sxs-lookup"><span data-stu-id="bd6b8-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="bd6b8-126">Visual Basic'de İşleç önceliği</span><span class="sxs-lookup"><span data-stu-id="bd6b8-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="bd6b8-127">İşlevselliğe göre listelenmiş işleçler</span><span class="sxs-lookup"><span data-stu-id="bd6b8-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="bd6b8-128">Deyimleri</span><span class="sxs-lookup"><span data-stu-id="bd6b8-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)