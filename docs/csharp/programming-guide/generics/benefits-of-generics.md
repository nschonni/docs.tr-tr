---
title: "Genel Türlerin Yararları (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9f46a328208b49aa33130a020e1a85b6f7aa7d97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="35323-102">Genel Türlerin Yararları (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="35323-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="35323-103">Genel türler sağlayan ortak dil çalışma zamanı ve C# dili içinde Genelleştirme gerçekleştirilir atama türleri için ve evrensel temel türü tarafından daha önceki sürümlerde bir sınırlama çözüme <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="35323-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="35323-104">Genel bir sınıf oluşturarak, tür kullanımı uyumlu bir koleksiyon oluşturabilirsiniz derleme zamanında.</span><span class="sxs-lookup"><span data-stu-id="35323-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="35323-105">Genel olmayan koleksiyon sınıfları kullanma sınırlamaları kullanır kısa bir program yazarak gösterilen <xref:System.Collections.ArrayList> .NET Framework Sınıf Kitaplığı'ndan koleksiyon sınıfı.</span><span class="sxs-lookup"><span data-stu-id="35323-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="35323-106"><xref:System.Collections.ArrayList>değişiklik yapmadan herhangi bir başvuru veya değer türü depolamak için kullanılan bir yüksek oranda uygun koleksiyonu sınıftır.</span><span class="sxs-lookup"><span data-stu-id="35323-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 <span data-ttu-id="35323-107">Ancak bu kullanışlı bir maliyetlerine neden olur.</span><span class="sxs-lookup"><span data-stu-id="35323-107">But this convenience comes at a cost.</span></span> <span data-ttu-id="35323-108">Eklenen herhangi bir başvuru veya değer türü bir <xref:System.Collections.ArrayList> için örtük olarak başvurmanıza olan <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="35323-108">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="35323-109">Değer türleri öğeler varsa bunlar listesine eklenir ve bunlar alınırken sarmalanmamış olduğunda bunlar Kutulu gerekir.</span><span class="sxs-lookup"><span data-stu-id="35323-109">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="35323-110">Atama ve kutulama ve kutudan çıkarma işlemleri performansını düşürebilir; kutulama ve kutudan çıkarma etkisini burada büyük koleksiyon yineleme senaryolarda çok önemli olabilir.</span><span class="sxs-lookup"><span data-stu-id="35323-110">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="35323-111">Diğer derleme zamanı tür denetimi eksiği kısıtlamadır; çünkü bir <xref:System.Collections.ArrayList> her şeye çevirir <xref:System.Object>, istemci kodu bunun gibi bir şey yapmasını önlemek için derleme zamanında bir yolu yoktur:</span><span class="sxs-lookup"><span data-stu-id="35323-111">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 <span data-ttu-id="35323-112">Edilebilir ve heterojen bir koleksiyon oluşturuyorsanız, bazen kasıtlı rağmen dizelerini birleştirme ve `ints` tek bir <xref:System.Collections.ArrayList> büyük olasılıkla bir programlama hatası olması ve bu hata çalışma zamanına kadar algılanmaz.</span><span class="sxs-lookup"><span data-stu-id="35323-112">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="35323-113">Sürümlerde 1.0 ve 1.1 C# dilinin, yalnızca kendi türü belirli koleksiyonlar yazarak .NET Framework temel sınıf kitaplığı koleksiyon sınıfları genelleştirilmiş kodda tehlikeleri önlemek.</span><span class="sxs-lookup"><span data-stu-id="35323-113">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="35323-114">Elbette, böyle bir sınıfın birden fazla veri türü için yeniden kullanılabilir olmadığından, Genelleştirme yararları kaybedebilirsiniz ve sınıfı depolanacak her tür için yeniden gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="35323-114">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="35323-115">Ne <xref:System.Collections.ArrayList> ve benzer diğer sınıflara gerçekten, kullanmayı düşündüğünüz belirli veri türüne bir örnek başına temelinde belirtmek istemci kodu için bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="35323-115">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="35323-116">Yukarı çevrim için gereksinimini ortadan `T:System.Object` ve ayrıca derleyici denetimi türü olası yapmak.</span><span class="sxs-lookup"><span data-stu-id="35323-116">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="35323-117">Diğer bir deyişle, <xref:System.Collections.ArrayList> bir tür parametresi gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="35323-117">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="35323-118">Tam olarak hangi genel türler sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="35323-118">That is exactly what generics provide.</span></span> <span data-ttu-id="35323-119">Genel olarak <xref:System.Collections.Generic.List%601> koleksiyonu içinde `N:System.Collections.Generic` ad alanı, öğeler koleksiyonuna eklenmeyi aynı işlemi bu benzer:</span><span class="sxs-lookup"><span data-stu-id="35323-119">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 <span data-ttu-id="35323-120">İçin istemci kodu, yalnızca eklenen sözdizimiyle <xref:System.Collections.Generic.List%601> karşılaştırılan <xref:System.Collections.ArrayList> bildirimi ve örnek oluşturma türü değişkeni.</span><span class="sxs-lookup"><span data-stu-id="35323-120">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="35323-121">Bu biraz daha kodlama karmaşıklık karşılığında yalnızca daha güvenli olmayan bir liste oluşturabilirsiniz <xref:System.Collections.ArrayList>, ancak Ayrıca önemli ölçüde daha hızlıdır, özellikle liste öğeleri değer türleri olduğunda.</span><span class="sxs-lookup"><span data-stu-id="35323-121">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35323-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35323-122">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="35323-123">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="35323-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="35323-124">Genel türlere giriş</span><span class="sxs-lookup"><span data-stu-id="35323-124">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="35323-125">Kutulama ve kutudan çıkarma</span><span class="sxs-lookup"><span data-stu-id="35323-125">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
 [<span data-ttu-id="35323-126">Koleksiyonları en iyi uygulamalar</span><span class="sxs-lookup"><span data-stu-id="35323-126">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)