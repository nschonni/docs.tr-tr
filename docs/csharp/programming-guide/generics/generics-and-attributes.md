---
title: "Genel Türler ve Öznitelikler (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5535334514afb0b9891dfce2e0cc0a0e95526069
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="52563-102">Genel Türler ve Öznitelikler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="52563-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="52563-103">Öznitelikler genel türleri için genel olmayan türleri aynı şekilde uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="52563-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="52563-104">Öznitelikleri uygulama ile ilgili daha fazla bilgi için bkz: [öznitelikleri](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="52563-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="52563-105">Özel öznitelikler yalnızca hiçbir tür bağımsız değişkenleri sağlanan genel türler ve tüm tür parametreleri için bağımsız değişkenleri eklemek kapalı oluşturulan genel türleri, açık genel türler başvurmak için izin verilir.</span><span class="sxs-lookup"><span data-stu-id="52563-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="52563-106">Aşağıdaki örnekler, bu özel öznitelik kullanın:</span><span class="sxs-lookup"><span data-stu-id="52563-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 <span data-ttu-id="52563-107">Açık genel tür bir öznitelik başvurusu yapabilir:</span><span class="sxs-lookup"><span data-stu-id="52563-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 <span data-ttu-id="52563-108">Uygun sayıda virgül kullanarak birden çok tür parametreleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="52563-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="52563-109">Bu örnekte, `GenericClass2` iki tür parametreye sahiptir:</span><span class="sxs-lookup"><span data-stu-id="52563-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 <span data-ttu-id="52563-110">Bir öznitelik kapalı oluşturulan genel bir tür başvurabilir:</span><span class="sxs-lookup"><span data-stu-id="52563-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 <span data-ttu-id="52563-111">Genel tür parametresi başvuruda bulunan bir öznitelik, bir derleme zamanı hatası neden olur:</span><span class="sxs-lookup"><span data-stu-id="52563-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 <span data-ttu-id="52563-112">Genel bir tür devralınmalıdır olamaz <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="52563-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 <span data-ttu-id="52563-113">Çalışma zamanında bir genel tür veya tür parametresi hakkında bilgi almak için yöntemleri kullanabilirsiniz <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="52563-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="52563-114">Daha fazla bilgi için bkz: [genel türler ve yansıma](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="52563-114">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52563-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="52563-115">See Also</span></span>  
 [<span data-ttu-id="52563-116">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="52563-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="52563-117">Genel türler</span><span class="sxs-lookup"><span data-stu-id="52563-117">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="52563-118">Öznitelikleri</span><span class="sxs-lookup"><span data-stu-id="52563-118">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)