---
title: Diziler (F#)
description: "Oluşturma ve diziler F # programlama dilini kullanma hakkında bilgi edinin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 61fa9084-abdc-4cf5-8213-91ec1211866b
ms.openlocfilehash: 7c9d8405230f4d765d3afdeaa154ddc598d0d1ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="arrays"></a><span data-ttu-id="b28cf-104">Diziler</span><span class="sxs-lookup"><span data-stu-id="b28cf-104">Arrays</span></span>

> [!NOTE]
<span data-ttu-id="b28cf-105">API başvuru bağlantısı sizi MSDN'ye götürür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-105">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="b28cf-106">Docs.microsoft.com API Başvurusu tamamlanmadı.</span><span class="sxs-lookup"><span data-stu-id="b28cf-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="b28cf-107">Diziler, ardışık veri öğelerinin tümü aynı türde sabit boyutlu, sıfır tabanlı, değişebilir koleksiyonlarıdır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-107">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="b28cf-108">Diziler oluşturma</span><span class="sxs-lookup"><span data-stu-id="b28cf-108">Creating Arrays</span></span>
<span data-ttu-id="b28cf-109">Diziler çeşitli yollarla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-109">You can create arrays in several ways.</span></span> <span data-ttu-id="b28cf-110">Küçük bir dizi ardışık değerler arasında listeleyerek oluşturabileceğiniz `[|` ve `|]` ve aşağıdaki örneklerde gösterildiği gibi noktalı virgülle ayırarak.</span><span class="sxs-lookup"><span data-stu-id="b28cf-110">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="b28cf-111">Bu gibi durumlarda, her öğe Ayrıca isteğe bağlı durumda noktalı virgül ayırıcısını ayrı bir satırda koyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-111">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="b28cf-112">Dizi öğelerin türü kullanılan değişmez değerleri algılanır ve tutarlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-112">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="b28cf-113">Aşağıdaki kod, 2 ve 3 float 1.0 olan ve tamsayılar olduğundan hataya neden olur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-113">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="b28cf-114">Sequence ifadeleri, dizi oluşturmak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-114">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="b28cf-115">Aşağıda 1'den 10'a bir dizi kare tamsayıların oluşturan bir örnek verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-115">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="b28cf-116">Hangi tüm öğeleri sıfır kullanılacağı başlatılır bir dizi oluşturmak için `Array.zeroCreate`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-116">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]
    
## <a name="accessing-elements"></a><span data-ttu-id="b28cf-117">Öğelere erişme</span><span class="sxs-lookup"><span data-stu-id="b28cf-117">Accessing Elements</span></span>

<span data-ttu-id="b28cf-118">Nokta işleci kullanarak dizi öğeleri erişebilirsiniz (`.`) ve parantezler (`[` ve `]`).</span><span class="sxs-lookup"><span data-stu-id="b28cf-118">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="b28cf-119">Dizi dizini 0'da başlatın.</span><span class="sxs-lookup"><span data-stu-id="b28cf-119">Array indexes start at 0.</span></span>

<span data-ttu-id="b28cf-120">Dizi öğeleri dizinin alt aralığı belirtmenize olanak tanıyan dilim gösterimini kullanarak da erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-120">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="b28cf-121">Dilim gösterimi örnekleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-121">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="b28cf-122">Dilim gösterimi kullanıldığında, dizi yeni bir kopyası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-122">When slice notation is used, a new copy of the array is created.</span></span>


## <a name="array-types-and-modules"></a><span data-ttu-id="b28cf-123">Dizi türleri ve modülleri</span><span class="sxs-lookup"><span data-stu-id="b28cf-123">Array Types and Modules</span></span>
<span data-ttu-id="b28cf-124">Tüm F # dizi türü .NET Framework türüdür <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b28cf-124">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b28cf-125">Bu nedenle, F # dizileri bulunan tüm işlevselliği desteklemek <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b28cf-125">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b28cf-126">Kitaplık Modülü [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) tek boyutlu diziler işlemlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="b28cf-126">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="b28cf-127">Modülleri `Array2D`, `Array3D`, ve `Array4D` dizileri üzerinde işlemler iki, üç ve dört boyut sırasıyla destek işlevler içerir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-127">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="b28cf-128">Rank dizileri dört kullanarak sıfırdan oluşturabilir <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b28cf-128">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="b28cf-129">Basit işlevleri</span><span class="sxs-lookup"><span data-stu-id="b28cf-129">Simple Functions</span></span>
<span data-ttu-id="b28cf-130">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc)bir öğeyi alır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-130">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="b28cf-131">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f)bir dizi uzunluğu, sağlar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-131">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="b28cf-132">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)bir öğe için belirtilen değere ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-132">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="b28cf-133">Aşağıdaki kod örneği, bu işlevler kullanımını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-133">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="b28cf-134">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-134">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="b28cf-135">Diziler oluşturma işlevleri</span><span class="sxs-lookup"><span data-stu-id="b28cf-135">Functions That Create Arrays</span></span>

<span data-ttu-id="b28cf-136">Çeşitli işlevler, var olan bir dizi gerek kalmadan diziler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="b28cf-136">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="b28cf-137">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32)herhangi bir öğe içermiyor yeni bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-137">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="b28cf-138">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be)Belirtilen boyutta bir dizi oluşturur ve sağlanan değerlere tüm öğelerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-138">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="b28cf-139">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665)bir dizi verilen boyut ve öğeleri oluşturmak için bir işlev oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-139">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="b28cf-140">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)içinde tüm öğeleri sıfır değeri dizinin türü için başlatılan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-140">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="b28cf-141">Aşağıdaki kod, bu işlevler gösterir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-141">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="b28cf-142">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-142">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="b28cf-143">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f)Varolan dizisinden kopyalanır öğeleri içeren yeni bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-143">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="b28cf-144">Kopya öğe türüne bir başvuru türü ise yalnızca başvuru kopyalanır anlamına gelir basit bir kopyası olduğunu unutmayın, temel alınan nesnesi değil.</span><span class="sxs-lookup"><span data-stu-id="b28cf-144">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="b28cf-145">Aşağıdaki kod örneği bunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-145">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="b28cf-146">Önceki kod çıkışı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-146">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="b28cf-147">Dize `Test1` yeni bir öğe oluşturma işlemi başvurusunda yazdığından yalnızca ilk dizisinde görünür `firstArray` içinde hala mevcut olduğu boş bir dize özgün referansı etkilemez ancak `secondArray`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-147">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="b28cf-148">Dize `Test2` çünkü her iki dizilerde görünür `Insert` işlemi <xref:System.Text.StringBuilder?displayProperty=nameWithType> türü etkiler arka plandaki <xref:System.Text.StringBuilder?displayProperty=nameWithType> hem dizilerde başvurulan nesne.</span><span class="sxs-lookup"><span data-stu-id="b28cf-148">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="b28cf-149">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d)Yeni bir dizi bir dizi alt aralığı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-149">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="b28cf-150">Başlangıç dizini ve uzunluk sağlayarak alt aralığı belirtin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-150">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="b28cf-151">Aşağıdaki kod kullanımını gösteren `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-151">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="b28cf-152">Çıkış subarray 5 öğede başlar ve 10 öğeleri içeren gösterir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-152">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
<span data-ttu-id="b28cf-153">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911)Yeni bir dizi varolan dizilerinin birleştirerek oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-153">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="b28cf-154">Aşağıdaki kodda **Array.append**.</span><span class="sxs-lookup"><span data-stu-id="b28cf-154">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="b28cf-155">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-155">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="b28cf-156">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09)Yeni bir dizi dahil etmek için bir dizi öğeleri seçer.</span><span class="sxs-lookup"><span data-stu-id="b28cf-156">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="b28cf-157">Aşağıdaki kodda `Array.choose`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-157">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="b28cf-158">Dizi öğesi türü seçenek türü döndürülen değer türüyle eşleşecek şekilde yok unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b28cf-158">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="b28cf-159">Bu örnekte, öğe türü olan `int` ve seçeneği polinom işlevin sonucu `elem*elem - 1`, olarak bir kayan nokta sayısı.</span><span class="sxs-lookup"><span data-stu-id="b28cf-159">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="b28cf-160">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-160">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="b28cf-161">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a)Belirtilen işlev var olan bir dizi her dizi öğesi üzerinde çalışır ve işlev tarafından oluşturulan öğelerin toplar ve bunları yeni bir dizi birleştirir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-161">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="b28cf-162">Aşağıdaki kodda `Array.collect`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-162">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="b28cf-163">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-163">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="b28cf-164">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302)diziler dizisi alır ve bunları tek bir dizi birleştirir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-164">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="b28cf-165">Aşağıdaki kodda `Array.concat`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-165">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="b28cf-166">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-166">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="b28cf-167">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede)Boole koşul işlevi alır ve yalnızca koşulun doğru olması Giriş dizisinden öğeleri içeren yeni bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-167">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="b28cf-168">Aşağıdaki kodda `Array.filter`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-168">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="b28cf-169">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-169">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="b28cf-170">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709)Yeni bir dizi var olan bir dizi sırasını döndürerek oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-170">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="b28cf-171">Aşağıdaki kodda `Array.rev`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-171">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

<span data-ttu-id="b28cf-172">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-172">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="b28cf-173">Ardışık Düzen işleci kullanılarak dizilerin dönüştürme işlevleri dizi modülünde kolayca birleştirebilirsiniz (`|>`), aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="b28cf-173">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="b28cf-174">Çıktı</span><span class="sxs-lookup"><span data-stu-id="b28cf-174">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="b28cf-175">Çok Boyutlu Diziler</span><span class="sxs-lookup"><span data-stu-id="b28cf-175">Multidimensional Arrays</span></span>

<span data-ttu-id="b28cf-176">Çok boyutlu bir diziye oluşturulabilir ancak sabit boyutlu bir diziye yazmak için hiçbir sözdizimi vardır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-176">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="b28cf-177">İşleç kullanma [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) bir dizi bir dizi öğelerin sıralarının serisinden oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-177">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="b28cf-178">Dizileri dizi ya da liste değişmez değerleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-178">The sequences can be array or list literals.</span></span> <span data-ttu-id="b28cf-179">Örneğin, aşağıdaki kod iki boyutlu bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-179">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="b28cf-180">İşlevi de kullanabilirsiniz [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) dizi iki boyutlarının ve benzer başlatmak için işlevleri üç ve dört boyutları diziler için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-180">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="b28cf-181">Bu işlevler öğeleri oluşturmak için kullanılan bir işlev alın.</span><span class="sxs-lookup"><span data-stu-id="b28cf-181">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="b28cf-182">Bir işlev belirtme yerine ilk bir değere ayarlayın öğeleri içeren iki boyutlu bir dizi oluşturmak için kullanın [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) için de kullanılabilir işlevi diziler en fazla dört boyut.</span><span class="sxs-lookup"><span data-stu-id="b28cf-182">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="b28cf-183">Aşağıdaki kod örneğinde ilk oluşan istediğiniz öğeleri içeren bir dizi oluşturulacağını gösterir ve ardından kullanır `Array2D.init` istenen iki boyutlu dizi oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-183">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="b28cf-184">Dizin oluşturma ve sözdizimi dilimleme dizi derece 4 kadar diziler için desteklenir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-184">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="b28cf-185">Birden çok boyutlarında dizin belirttiğinizde, virgül dizinler, aşağıdaki kod örneğinde gösterildiği gibi kullanın.</span><span class="sxs-lookup"><span data-stu-id="b28cf-185">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]
    
<span data-ttu-id="b28cf-186">İki boyutlu bir dizi türü olarak yazılır `<type>[,]` (örneğin, `int[,]`, `double[,]`), ve üç boyutlu bir dizi türü olarak yazılır `<type>[,,]`, daha yüksek boyutlarının dizileri ve benzeri için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-186">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="b28cf-187">Tek boyutlu diziler için kullanılabilen işlevleri yalnızca bir kısmı ayrıca çok boyutlu diziler için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-187">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="b28cf-188">Daha fazla bilgi için bkz: [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), ve [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="b28cf-188">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="b28cf-189">Dizi dilimleme ve çok boyutlu diziler</span><span class="sxs-lookup"><span data-stu-id="b28cf-189">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="b28cf-190">İki boyutlu bir dizi içinde (matrisi), bir alt matris aralıkları belirtme ve bir joker karakter kullanılması ayıklayabilirsiniz (`*`) karakter tüm satırları veya sütunları belirtin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-190">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
/ Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="b28cf-191">F # 3.1 sürümünden itibaren aynı veya daha düşük boyut subarrays boyutlu bir diziye bozabilir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-191">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="b28cf-192">Örneğin, tek bir satır veya sütun belirterek bir matristen vektör edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-192">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="b28cf-193">Bu öğe erişim işleçler ve aşırı türleri için sözdizimi dilimleme kullanmak `GetSlice` yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="b28cf-193">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="b28cf-194">Örneğin, F # 2B dizi sarmalar, dizi dizin oluşturma işlemi için destek sağlamak için bir öğe özelliği uygulayan ve üç sürümü uygulayan bir matris türü aşağıdaki kodu oluşturur `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-194">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="b28cf-195">Bu kod, matris türleri için bir şablon olarak kullanabilirsiniz, bu bölümde açıklanmıştır dilimleme işlemlerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-195">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart = 
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart = 
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish = 
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart = 
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish = 
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart = 
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish = 
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="b28cf-196">Diziler Boolean işlevleri</span><span class="sxs-lookup"><span data-stu-id="b28cf-196">Boolean Functions on Arrays</span></span>

<span data-ttu-id="b28cf-197">İşlevler [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) ve [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) öğelerini sırasıyla bir veya iki dizilerde test.</span><span class="sxs-lookup"><span data-stu-id="b28cf-197">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="b28cf-198">Bu işlevlerin bir sınama işlevini alın ve dönüş `true` bir öğe yoksa (veya öğesi çifti için `Array.exists2`) koşulu karşılayan.</span><span class="sxs-lookup"><span data-stu-id="b28cf-198">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="b28cf-199">Aşağıdaki kod kullanımını gösteren `Array.exists` ve `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-199">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="b28cf-200">Bu örneklerde, bu durumda, işlevi bağımsız değişken bağımsız değişken yalnızca birini uygulayarak yeni işlevler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-200">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="b28cf-201">Önceki kod çıkışı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-201">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="b28cf-202">Benzer şekilde, işlevi [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) her öğe bir Boolean koşulu karşılayıp karşılamadığını belirlemek için bir dizi sınar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-202">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="b28cf-203">Değişim [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) eşit uzunlukta iki dizi öğeleri içeren bir Boolean işlevini kullanarak aynı şeyi yapar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-203">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="b28cf-204">Aşağıdaki kod Bu işlevlerden birinin kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-204">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="b28cf-205">Bu örnekler için çıktı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-205">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="b28cf-206">Arama diziler</span><span class="sxs-lookup"><span data-stu-id="b28cf-206">Searching Arrays</span></span>

<span data-ttu-id="b28cf-207">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33)Boolean işlevi alır ve işlevin döndüğü ilk öğeyi döndürür `true`, veya başlatır bir <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> koşulu karşılayan herhangi bir öğe bulunursa.</span><span class="sxs-lookup"><span data-stu-id="b28cf-207">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="b28cf-208">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f)benzer `Array.find`, ancak bu öğenin kendisi yerine öğenin dizinini döndürür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-208">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="b28cf-209">Aşağıdaki kod `Array.find` ve `Array.findIndex` bir mükemmel kare ve mükemmel küpe numarasını bulmak için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-209">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="b28cf-210">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-210">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="b28cf-211">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9)benzer `Array.find`sonucunu bir seçenek türü ve onu döndürür dışında `None` hiçbir öğe bulunursa.</span><span class="sxs-lookup"><span data-stu-id="b28cf-211">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="b28cf-212">`Array.tryFind`yerine kullanılmalıdır `Array.find` değil bildiğinizde eşleşen bir öğe dizide olup olmadığını.</span><span class="sxs-lookup"><span data-stu-id="b28cf-212">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="b28cf-213">Benzer şekilde, [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) benzer [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) dışında bu seçenek türü dönüş değeri değil.</span><span class="sxs-lookup"><span data-stu-id="b28cf-213">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="b28cf-214">Hiçbir öğe bulunursa, seçenektir `None`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-214">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="b28cf-215">Aşağıdaki kod kullanımını gösteren `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-215">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="b28cf-216">Bu kod, önceki koduna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-216">This code depends on the previous code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="b28cf-217">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-217">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="b28cf-218">Kullanım [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) bulmakta ek olarak bir öğe dönüştürmek gerektiğinde.</span><span class="sxs-lookup"><span data-stu-id="b28cf-218">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="b28cf-219">Sonuç, işlevi döndürür bir seçenek değeri olarak dönüştürülmüş öğenin ilk öğedir veya `None` böyle bir öğe bulunursa.</span><span class="sxs-lookup"><span data-stu-id="b28cf-219">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="b28cf-220">Aşağıdaki kod kullanımı gösterilmiştir `Array.tryPick`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-220">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="b28cf-221">Bu durumda, bir lambda ifadesi yerine birkaç yerel yardımcı işlevleri kodu basitleştirmek için tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-221">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="b28cf-222">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-222">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="b28cf-223">Dizileri hesaplamalar gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="b28cf-223">Performing Computations on Arrays</span></span>

<span data-ttu-id="b28cf-224">[ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) İşlevi bir dizi her öğe ortalamasını döndürür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-224">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="b28cf-225">Kayan nokta türleri ancak olmayan tam sayı türleri içeren bir tamsayı tam bölme destekleyen öğe türleri için sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-225">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="b28cf-226">[ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) İşlevi her öğe üzerinde bir işlev çağırma sonuçları ortalamasını döndürür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-226">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="b28cf-227">Tamsayı türünde bir dizi için kullandığınız `Array.averageBy` ve kayan her öğeye Dönüştür işlevi noktası hesaplama türü.</span><span class="sxs-lookup"><span data-stu-id="b28cf-227">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="b28cf-228">Kullanım [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) veya [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) öğe türü destekliyorsa, en düşük veya en fazla öğe alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="b28cf-228">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="b28cf-229">Benzer şekilde, [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) ve [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) önce yürütülecek, belki de karşılaştırma destekleyen türüne dönüştürmek için bir işlev izin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-229">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="b28cf-230">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2)bir dizinin öğeleri ekler ve [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) her öğe üzerinde bir işlevini çağırır ve sonuçları bir araya getirir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-230">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="b28cf-231">Dönüş değerleri depolamadan dizideki her öğe üzerinde bir işlev yürütmek için kullanın [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="b28cf-231">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="b28cf-232">İki dizi eşit uzunlukta içeren bir işlevi için [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="b28cf-232">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="b28cf-233">Bir dizi işlevinin sonuçlarını tutmak ihtiyacınız varsa, kullanmak [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) veya [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), aynı anda iki diziler üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="b28cf-233">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="b28cf-234">Çeşitlemeleri [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) ve [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) hesaplama yer alması için öğenin dizini izin ver; aynı için doğrudur [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) ve [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="b28cf-234">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="b28cf-235">İşlevler [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), ve [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) bir dizinin tüm öğeleri içeren algoritmaları yürütün.</span><span class="sxs-lookup"><span data-stu-id="b28cf-235">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="b28cf-236">Benzer şekilde, Çeşitlemeler [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) ve [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) iki dizilerinde hesaplamalar gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-236">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="b28cf-237">Aynı adlı işlevleri hesaplamalar gerçekleştirmek için bu işlevler karşılık [List Modülü](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="b28cf-237">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="b28cf-238">Kullanım örnekleri için bkz: [listeler](lists.md).</span><span class="sxs-lookup"><span data-stu-id="b28cf-238">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="b28cf-239">Diziler değiştirme</span><span class="sxs-lookup"><span data-stu-id="b28cf-239">Modifying Arrays</span></span>

<span data-ttu-id="b28cf-240">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)bir öğe için belirtilen değere ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-240">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="b28cf-241">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2)belirli bir değere bir dizide öğe aralığını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-241">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="b28cf-242">Aşağıdaki kod örneği sağlar `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-242">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="b28cf-243">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b28cf-243">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="b28cf-244">Kullanabileceğiniz [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) başka diziye bir dizi alt kopyalanacak.</span><span class="sxs-lookup"><span data-stu-id="b28cf-244">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="b28cf-245">İçin ve diğer türleri dönüştürme</span><span class="sxs-lookup"><span data-stu-id="b28cf-245">Converting to and from Other Types</span></span>

<span data-ttu-id="b28cf-246">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b)bir dizi listesinden bir liste oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-246">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="b28cf-247">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c)bir dizi bir dizisini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b28cf-247">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="b28cf-248">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786)ve [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) dizi türünden diğer bu koleksiyon türleri dönüştürmek.</span><span class="sxs-lookup"><span data-stu-id="b28cf-248">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="b28cf-249">Sıralama dizileri</span><span class="sxs-lookup"><span data-stu-id="b28cf-249">Sorting Arrays</span></span>

<span data-ttu-id="b28cf-250">Kullanım [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) genel karşılaştırma işlevini kullanarak bir dizi sıralamak için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-250">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="b28cf-251">Kullanım [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) bir değer oluşturan bir işlev belirtmek için olarak bilinir bir *anahtar*anahtarı genel karşılaştırma işlevini kullanarak sıralama için.</span><span class="sxs-lookup"><span data-stu-id="b28cf-251">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="b28cf-252">Kullanım [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) özel karşılaştırma işlevi sağlamak istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="b28cf-252">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="b28cf-253">`Array.sort`, `Array.sortBy`, ve `Array.sortWith` tüm yeni bir dizi olarak sıralanmış dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-253">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="b28cf-254">Çeşitlemeleri [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), ve [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) yeni bir döndürme yerine mevcut dizisini değiştirin.</span><span class="sxs-lookup"><span data-stu-id="b28cf-254">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="b28cf-255">Diziler ve diziler</span><span class="sxs-lookup"><span data-stu-id="b28cf-255">Arrays and Tuples</span></span>

<span data-ttu-id="b28cf-256">İşlevler [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) ve [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) dizi ve diziler tanımlama grubu çiftleri dizileri Dönüştür.</span><span class="sxs-lookup"><span data-stu-id="b28cf-256">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="b28cf-257">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d)ve [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) üç öğelerinin diziler veya üç dizi diziler çalışmak benzer.</span><span class="sxs-lookup"><span data-stu-id="b28cf-257">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="b28cf-258">Diziler üzerinde paralel hesaplamalar</span><span class="sxs-lookup"><span data-stu-id="b28cf-258">Parallel Computations on Arrays</span></span>

<span data-ttu-id="b28cf-259">Modül [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) diziler üzerinde paralel hesaplamalar gerçekleştirmek için işlevler içerir.</span><span class="sxs-lookup"><span data-stu-id="b28cf-259">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="b28cf-260">Bu modül, .NET Framework 4. sürümden önceki sürümlerini hedefleyen uygulamalar de kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-260">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="b28cf-261">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b28cf-261">See Also</span></span>
[<span data-ttu-id="b28cf-262">F # dili başvurusu</span><span class="sxs-lookup"><span data-stu-id="b28cf-262">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b28cf-263">F #'TA; Türler</span><span class="sxs-lookup"><span data-stu-id="b28cf-263">F#; Types</span></span>](fsharp-types.md)