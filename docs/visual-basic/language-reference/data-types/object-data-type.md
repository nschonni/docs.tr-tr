---
title: "Nesne Veri Türü"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="924dc-102">Nesne Veri Türü</span><span class="sxs-lookup"><span data-stu-id="924dc-102">Object Data Type</span></span>
<span data-ttu-id="924dc-103">Nesnelere atıfta adresleri tutar.</span><span class="sxs-lookup"><span data-stu-id="924dc-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="924dc-104">Herhangi bir başvuru türü (dize, dizi, sınıf veya arabirim) atayabileceğiniz bir `Object` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="924dc-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="924dc-105">Bir `Object` değişkeni ayrıca herhangi bir değer türde veri bakın (sayısal, `Boolean`, `Char`, `Date`, yapı veya sabit listesi).</span><span class="sxs-lookup"><span data-stu-id="924dc-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="924dc-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="924dc-106">Remarks</span></span>  
 <span data-ttu-id="924dc-107">`Object` Veri türü, uygulamanızın tanıdığı herhangi bir nesne örneği de dahil olmak üzere, herhangi bir veri türü veri noktası.</span><span class="sxs-lookup"><span data-stu-id="924dc-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="924dc-108">Kullanım `Object` derleme zamanında bilmiyorsanız değişkeni hangi veri türü işaret.</span><span class="sxs-lookup"><span data-stu-id="924dc-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="924dc-109">Varsayılan değer olan `Object` olan `Nothing` (bir null başvuru).</span><span class="sxs-lookup"><span data-stu-id="924dc-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="924dc-110">Veri Türleri</span><span class="sxs-lookup"><span data-stu-id="924dc-110">Data Types</span></span>  
 <span data-ttu-id="924dc-111">Bir değişken, sabit veya herhangi bir veri türü için bir ifade atayabilirsiniz bir `Object` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="924dc-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="924dc-112">Veri türü belirlemek için bir `Object` değişkeni şu anda başvurduğu, kullanabileceğiniz <xref:System.Type.GetTypeCode%2A> yöntemi <xref:System.Type?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="924dc-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="924dc-113">Aşağıdaki örnek bunu göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="924dc-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="924dc-114">`Object` Veri türü olan bir başvuru türü.</span><span class="sxs-lookup"><span data-stu-id="924dc-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="924dc-115">Ancak, Visual Basic değerlendirir bir `Object` değişken olarak bir değer türü veri başvurduğunda bir değer türü.</span><span class="sxs-lookup"><span data-stu-id="924dc-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="924dc-116">Depolama</span><span class="sxs-lookup"><span data-stu-id="924dc-116">Storage</span></span>  
 <span data-ttu-id="924dc-117">Başvurduğu için hangi veri türü bir `Object` değişkeni kendisini ancak bunun yerine bir işaretçi değeri için veri değeri içermiyor.</span><span class="sxs-lookup"><span data-stu-id="924dc-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="924dc-118">Her zaman bilgisayar belleğinde dört bayt kullanır, ancak bu değişkenin değerini temsil eden veri depolama içermez.</span><span class="sxs-lookup"><span data-stu-id="924dc-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="924dc-119">İşaretçinin verileri bulmak için kullandığı kodu nedeniyle `Object` değer türleri bulunduran değişkenleri daha açık olarak belirtilmiş değişkenleri erişmek biraz daha yavaş.</span><span class="sxs-lookup"><span data-stu-id="924dc-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="924dc-120">Programlama İpuçları</span><span class="sxs-lookup"><span data-stu-id="924dc-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="924dc-121">**Birlikte çalışma hakkında dikkat edilecek noktalar**</span><span class="sxs-lookup"><span data-stu-id="924dc-121">**Interop Considerations.**</span></span> <span data-ttu-id="924dc-122">Örnek otomasyon veya COM nesneleri için .NET Framework için yazılmaz bileşenleriyle arabirim, diğer ortamlarda işaretçi türleri Visual Basic ile uyumlu olmayan göz önünde bulundurmanız `Object` türü.</span><span class="sxs-lookup"><span data-stu-id="924dc-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="924dc-123">**Performans.**</span><span class="sxs-lookup"><span data-stu-id="924dc-123">**Performance.**</span></span> <span data-ttu-id="924dc-124">Bir değişken bildirme ile `Object` türüdür herhangi bir nesneye başvuru içeren için yeterince esnektir.</span><span class="sxs-lookup"><span data-stu-id="924dc-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="924dc-125">Ancak, bir yöntemi veya özelliği gibi bir değişken çağırdığınızda, her zaman tabi *geç bağlama* (çalışma zamanında).</span><span class="sxs-lookup"><span data-stu-id="924dc-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="924dc-126">Zorlamak için *erken bağlama* (derleme zamanında) ve daha iyi performans, belirli bir sınıf ada sahip bir değişken bildirme veya belirli veri türüne dönüştürün.</span><span class="sxs-lookup"><span data-stu-id="924dc-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="924dc-127">Bir nesne değişkeni bildirme, belirli bir sınıf türü, örneğin kullanmaya çalıştığınızda <xref:System.OperatingSystem>, genelleştirilmiş yerine `Object` türü.</span><span class="sxs-lookup"><span data-stu-id="924dc-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="924dc-128">Ayrıca gibi kullanılabilir en belirgin sınıfını kullanmalısınız <xref:System.Windows.Forms.TextBox> yerine <xref:System.Windows.Forms.Control>, böylece özelliklerini ve yöntemlerini erişebilir.</span><span class="sxs-lookup"><span data-stu-id="924dc-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="924dc-129">Genellikle kullanabilirsiniz **sınıfları** listesinde **Nesne Tarayıcısı** kullanılabilir sınıf adlarını bulmak için.</span><span class="sxs-lookup"><span data-stu-id="924dc-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="924dc-130">**Genişletme.**</span><span class="sxs-lookup"><span data-stu-id="924dc-130">**Widening.**</span></span> <span data-ttu-id="924dc-131">Tüm veri türleri ve tüm başvuru türleri için genişletmek `Object` veri türü.</span><span class="sxs-lookup"><span data-stu-id="924dc-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="924dc-132">Bu dönüştürme için herhangi bir türü anlamına gelir `Object` karşılaşmadan olmadan bir <xref:System.OverflowException?displayProperty=nameWithType> hata.</span><span class="sxs-lookup"><span data-stu-id="924dc-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="924dc-133">Ancak, değer türleri arasında dönüştürürseniz ve `Object`, Visual Basic adlı işlemler gerçekleştirdiğinde *kutulama* ve *kutudan çıkarma*, yürütme yavaş olun.</span><span class="sxs-lookup"><span data-stu-id="924dc-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="924dc-134">**Karakterleri yazın.**</span><span class="sxs-lookup"><span data-stu-id="924dc-134">**Type Characters.**</span></span> <span data-ttu-id="924dc-135">`Object`değişmez değer türü karakteri ya da tanımlayıcı türü karakteri içeriyor.</span><span class="sxs-lookup"><span data-stu-id="924dc-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="924dc-136">**Framework türü.**</span><span class="sxs-lookup"><span data-stu-id="924dc-136">**Framework Type.**</span></span> <span data-ttu-id="924dc-137">.NET Framework'teki karşılık gelen tür <xref:System.Object?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="924dc-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="924dc-138">Örnek</span><span class="sxs-lookup"><span data-stu-id="924dc-138">Example</span></span>  
 <span data-ttu-id="924dc-139">Aşağıdaki örnek gösterilmektedir bir `Object` işaret eden bir nesne örneğine değişkeni.</span><span class="sxs-lookup"><span data-stu-id="924dc-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="924dc-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="924dc-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="924dc-141">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="924dc-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="924dc-142">Tür dönüşüm işlevleri</span><span class="sxs-lookup"><span data-stu-id="924dc-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="924dc-143">Dönüştürme özeti</span><span class="sxs-lookup"><span data-stu-id="924dc-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="924dc-144">Veri türlerinin etkili kullanımı</span><span class="sxs-lookup"><span data-stu-id="924dc-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="924dc-145">Nasıl yapılır: iki nesnenin ilgili olup olmadığını belirleme</span><span class="sxs-lookup"><span data-stu-id="924dc-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="924dc-146">Nasıl yapılır: iki nesnenin aynı olup olmadığını belirleme</span><span class="sxs-lookup"><span data-stu-id="924dc-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)