---
title: "Örnek Oluşturucuları (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: efb82128ffc27a7c065d2ba12bfc08396d3b5cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="bb73b-102">Örnek Oluşturucuları (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="bb73b-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="bb73b-103">Örnek oluşturucuları oluşturmak ve kullandığınızda herhangi bir örnek üye değişkeni başlatmak için kullanılan [yeni](../../../csharp/language-reference/keywords/new.md) bir nesne oluşturmak için ifade bir [sınıfı](../../../csharp/language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="bb73b-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="bb73b-104">Başlatmak için bir [statik](../../../csharp/language-reference/keywords/static.md) sınıfı ya da statik olmayan sınıftaki statik değişkenler statik Oluşturucu tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="bb73b-105">Daha fazla bilgi için bkz: [statik oluşturucular](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="bb73b-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="bb73b-106">Aşağıdaki örnek, örnek oluşturucu gösterir:</span><span class="sxs-lookup"><span data-stu-id="bb73b-106">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="bb73b-107">Daha anlaşılır olması için bu sınıf ortak alanları içerir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-107">For clarity, this class contains public fields.</span></span> <span data-ttu-id="bb73b-108">Genel alanlar kullanımını bir programı başka bir yerindeki herhangi bir yöntemini Kısıtlanmamış ve nesnenin çalışmalar erişimi doğrulanmamış izin verdiği için önerilen bir programlama uygulama değil.</span><span class="sxs-lookup"><span data-stu-id="bb73b-108">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="bb73b-109">Veri üyeleri genellikle özel olmalıdır ve yalnızca sınıfı yöntemleri ve özellikleri erişilmelidir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-109">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="bb73b-110">Bir nesne esas her Bu örnek oluşturucu çağrılır `CoOrds` sınıfı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="bb73b-110">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="bb73b-111">Bağımsız değişken almayan, bunu adlı gibi bir oluşturucu bir *varsayılan oluşturucu*.</span><span class="sxs-lookup"><span data-stu-id="bb73b-111">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="bb73b-112">Ancak, genellikle ek oluşturucular sağlamak yararlı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="bb73b-112">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="bb73b-113">Örneğin, bir oluşturucuya ekleyebiliriz `CoOrds` bize veri üyeleri için başlangıç değerlerini belirtmenizi sağlayan sınıfı:</span><span class="sxs-lookup"><span data-stu-id="bb73b-113">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 <span data-ttu-id="bb73b-114">Böylece `CoOrd` varsayılan veya özel ilk değerleri ile oluşturulan nesnelere şöyle:</span><span class="sxs-lookup"><span data-stu-id="bb73b-114">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 <span data-ttu-id="bb73b-115">Bir sınıf bir oluşturucuya sahip değilse, varsayılan bir oluşturucu otomatik olarak oluşturulur ve varsayılan değerler nesne alanları başlatmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bb73b-115">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="bb73b-116">Örneğin, bir [int](../../../csharp/language-reference/keywords/int.md) 0 olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="bb73b-116">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="bb73b-117">Varsayılan değerleri hakkında daha fazla bilgi için bkz: [varsayılan değerler tablosu](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="bb73b-117">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="bb73b-118">Bu nedenle, çünkü `CoOrds` sınıfı varsayılan oluşturucu, tüm veri üyeleri sıfırdan başlatır, sınıf nasıl çalıştığını değiştirmeden tamamen kaldırılabilir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-118">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="bb73b-119">Birden çok oluşturucuları kullanarak tam bir örnek daha sonra bu konudaki örnek 1'de sağlanan ve otomatik olarak oluşturulan bir oluşturucu örneği örnek 2'de sağlanır.</span><span class="sxs-lookup"><span data-stu-id="bb73b-119">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="bb73b-120">Örnek oluşturucuları, temel sınıflarının örnek oluşturucuları çağırmak için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-120">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="bb73b-121">Sınıf oluşturucu başlatıcı üzerinden temel sınıf gibi çağırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="bb73b-121">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 <span data-ttu-id="bb73b-122">Bu örnekte, `Circle` sınıfı tarafından sağlanan oluşturucuya RADIUS ve yükseklik gösteren değerlerin geçirir `Shape` içinden `Circle` türetilir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-122">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="bb73b-123">Kullanarak bir tam örnek `Shape` ve `Circle` bu konudaki örnek 3 olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="bb73b-123">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="bb73b-124">Örnek 1</span><span class="sxs-lookup"><span data-stu-id="bb73b-124">Example 1</span></span>  
 <span data-ttu-id="bb73b-125">Aşağıdaki örnek, iki sınıf oluşturucular ve bağımsız değişkenler olmadan bir iki bağımsız değişkeni ile bir sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-125">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="bb73b-126">Örnek 2</span><span class="sxs-lookup"><span data-stu-id="bb73b-126">Example 2</span></span>  
 <span data-ttu-id="bb73b-127">Bu örnekte, sınıf `Person` durumda, varsayılan bir oluşturucu otomatik olarak sağlanır ve alanları varsayılan değerlerine başlatılan tüm oluşturucular yok.</span><span class="sxs-lookup"><span data-stu-id="bb73b-127">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 <span data-ttu-id="bb73b-128">Dikkat varsayılan değerini `age` olan `0` ve varsayılan değerini `name` olan `null`.</span><span class="sxs-lookup"><span data-stu-id="bb73b-128">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="bb73b-129">Varsayılan değerleri hakkında daha fazla bilgi için bkz: [varsayılan değerler tablosu](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="bb73b-129">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="bb73b-130">Örnek 3</span><span class="sxs-lookup"><span data-stu-id="bb73b-130">Example 3</span></span>  
 <span data-ttu-id="bb73b-131">Aşağıdaki örnek, temel sınıf Başlatıcı kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="bb73b-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="bb73b-132">`Circle` Genel sınıfından türetilmiş sınıf `Shape`ve `Cylinder` sınıfı türetilir `Circle` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bb73b-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="bb73b-133">Her türetilmiş sınıf oluşturucu, temel sınıf Başlatıcısı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="bb73b-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 <span data-ttu-id="bb73b-134">Temel sınıf oluşturucular Çağırma ile ilgili daha fazla örnek için bkz: [sanal](../../../csharp/language-reference/keywords/virtual.md), [geçersiz kılma](../../../csharp/language-reference/keywords/override.md), ve [temel](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="bb73b-134">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb73b-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bb73b-135">See Also</span></span>  
 [<span data-ttu-id="bb73b-136">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="bb73b-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bb73b-137">Sınıflar ve yapılar</span><span class="sxs-lookup"><span data-stu-id="bb73b-137">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="bb73b-138">Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="bb73b-138">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="bb73b-139">Sonlandırıcılar</span><span class="sxs-lookup"><span data-stu-id="bb73b-139">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="bb73b-140">statik</span><span class="sxs-lookup"><span data-stu-id="bb73b-140">static</span></span>](../../../csharp/language-reference/keywords/static.md)