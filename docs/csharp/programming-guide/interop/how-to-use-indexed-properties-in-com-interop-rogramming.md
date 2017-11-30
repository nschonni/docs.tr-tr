---
title: "Nasıl yapılır: COM Birlikte Çalışma Programlamada Dizin Oluşturulmuş Özellikleri Kullanma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6ccd4248730d3c89528dad62b3f8ced3b9e42b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="d4a91-102">Nasıl yapılır: COM Birlikte Çalışma Programlamada Dizin Oluşturulmuş Özellikleri Kullanma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="d4a91-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="d4a91-103">*Dizin oluşturulmuş özellikleri* COM parametrelere sahip özellikleri tüketilen şeklini geliştirmek C# programlama içinde.</span><span class="sxs-lookup"><span data-stu-id="d4a91-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="d4a91-104">Diğer özellikler Visual C# ' ta, birlikte özellikleri iş gibi dizine [adlandırılmış ve isteğe bağlı bağımsız değişkenler](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), yeni bir tür ([dinamik](../../../csharp/language-reference/keywords/dynamic.md)), ve [katıştırılmış türde bilgi](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), Microsoft Office programlama geliştirin.</span><span class="sxs-lookup"><span data-stu-id="d4a91-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="d4a91-105">Önceki sürümlerde, C#, yöntemleri özellikleri yalnızca Eğer erişilebilir `get` yöntemi sahip herhangi bir parametre ve `set` yöntemi tek bir değer parametresine sahip.</span><span class="sxs-lookup"><span data-stu-id="d4a91-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="d4a91-106">Ancak, tüm COM özellikleri bu kısıtlamaları karşılar.</span><span class="sxs-lookup"><span data-stu-id="d4a91-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="d4a91-107">Örneğin, Excel [aralığı](http://go.microsoft.com/fwlink/?LinkId=166053) özelliğine sahip bir `get` aralığın adı için bir parametre gerektiren erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="d4a91-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="d4a91-108">Geçmişte, değil erişebilir çünkü `Range` özelliği doğrudan, sahip olduğunuz kullanmak `get_Range` yöntemi bunun yerine, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="d4a91-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 <span data-ttu-id="d4a91-109">Dizinli Özellikler, bunun yerine aşağıdaki yazma olanak sağlar:</span><span class="sxs-lookup"><span data-stu-id="d4a91-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="d4a91-110">Önceki örnekte de kullanır [isteğe bağlı bağımsız değişkenler](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) atlayın olanak tanıyan özellik `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="d4a91-110">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="d4a91-111">Benzer şekilde değerini ayarlamak için `Value` özelliği bir [aralığı](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) nesne Visual C# 2008 ve daha önceki sürümlerde, iki bağımsız değişkenleri gereklidir.</span><span class="sxs-lookup"><span data-stu-id="d4a91-111">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="d4a91-112">Bir aralık değeri türünü belirtir. isteğe bağlı bir parametre için bir bağımsız değişken sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4a91-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="d4a91-113">Diğer için değer sağlıyor `Value` özelliği.</span><span class="sxs-lookup"><span data-stu-id="d4a91-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="d4a91-114">Aşağıdaki örnekler, bu teknikleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="d4a91-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="d4a91-115">Her ikisi de A1 hücrenin değerini `Name`.</span><span class="sxs-lookup"><span data-stu-id="d4a91-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 <span data-ttu-id="d4a91-116">Dizinli Özellikler, bunun yerine aşağıdaki kod yazmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4a91-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 <span data-ttu-id="d4a91-117">Dizinli Özellikler kendi oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="d4a91-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="d4a91-118">Özelliği, yalnızca mevcut Dizinli Özellikler kullanımını destekler.</span><span class="sxs-lookup"><span data-stu-id="d4a91-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4a91-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="d4a91-119">Example</span></span>  
 <span data-ttu-id="d4a91-120">Aşağıdaki kod, tam bir örnek gösterilir.</span><span class="sxs-lookup"><span data-stu-id="d4a91-120">The following code shows a complete example.</span></span> <span data-ttu-id="d4a91-121">Office API erişen bir projeyi ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual C# özellikleri kullanarak erişim Office birlikte çalışma nesneleriyle](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d4a91-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d4a91-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d4a91-122">See Also</span></span>  
 [<span data-ttu-id="d4a91-123">Adlandırılmış ve isteğe bağlı bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="d4a91-123">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [<span data-ttu-id="d4a91-124">dinamik</span><span class="sxs-lookup"><span data-stu-id="d4a91-124">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="d4a91-125">Tür dinamiği kullanma</span><span class="sxs-lookup"><span data-stu-id="d4a91-125">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="d4a91-126">Nasıl yapılır: Office Programlamada adlandırılmış ve isteğe bağlı bağımsız değişkenleri kullanma</span><span class="sxs-lookup"><span data-stu-id="d4a91-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [<span data-ttu-id="d4a91-127">Nasıl yapılır: Visual C# özelliklerini kullanarak Office birlikte çalışma nesnelerine erişim</span><span class="sxs-lookup"><span data-stu-id="d4a91-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 [<span data-ttu-id="d4a91-128">İzlenecek yol: Office programlama</span><span class="sxs-lookup"><span data-stu-id="d4a91-128">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)