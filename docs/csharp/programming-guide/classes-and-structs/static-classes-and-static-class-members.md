---
title: "Statik Sınıflar ve Statik Sınıf Üyeleri (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: "49"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cf2517dd5989d36341b840ffcb476cbeb14baf54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="99c3b-102">Statik Sınıflar ve Statik Sınıf Üyeleri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="99c3b-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="99c3b-103">A [statik](../../../csharp/language-reference/keywords/static.md) sınıfı, aslında bir statik olmayan sınıf ile aynı, ancak bir fark yoktur: statik sınıf örneği oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="99c3b-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="99c3b-104">Diğer bir deyişle, kullanamazsınız [yeni](../../../csharp/language-reference/keywords/new.md) sınıfı türünde bir değişken oluşturmak için anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="99c3b-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="99c3b-105">Hiçbir örnek değişken olduğundan, statik sınıf üyeleri sınıf adı kullanarak erişir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="99c3b-106">Örneğin, bu sınıfı statik varsa adlı `UtilityClass` adlı ortak bir yöntemi olan `MethodA`, aşağıdaki örnekte gösterildiği gibi yöntemini çağırın:</span><span class="sxs-lookup"><span data-stu-id="99c3b-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="99c3b-107">Statik sınıf yalnızca giriş parametrelerine çalışan ve get veya tüm iç örneği alanları gerekmez yöntemleri kümeleri için uygun bir kapsayıcı olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="99c3b-108">Örneğin, .NET Framework Sınıf Kitaplığı'nda, statik <xref:System.Math?displayProperty=nameWithType> sınıfı içeren depolama veya belirli bir örneği için benzersiz olan veri almak için herhangi bir gereksinim olmadan matematik işlemlerini gerçekleştiren yöntemleri <xref:System.Math> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="99c3b-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=nameWithType> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="99c3b-109">Diğer bir deyişle, sınıf üyeleri sınıfı adı ve yöntem adını belirterek aşağıdaki örnekte gösterildiği gibi uygulayın.</span><span class="sxs-lookup"><span data-stu-id="99c3b-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="99c3b-110">Tüm sınıf türleri ile olduğu gibi statik sınıf için tür bilgisi tarafından yüklenen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ortak dil çalışma zamanı (CLR) sınıfı başvuran program yüklendiğinde.</span><span class="sxs-lookup"><span data-stu-id="99c3b-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="99c3b-111">Program, tam olarak ne zaman sınıfı yüklenen belirtemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="99c3b-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="99c3b-112">Ancak, yüklenmesi ve başlatılan alanlarını ve sınıf programınızdaki ilk kez başvuruluyor önce çağırılır, statik Oluşturucusu sağlanır.</span><span class="sxs-lookup"><span data-stu-id="99c3b-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="99c3b-113">Statik Oluşturucu yalnızca bir kez çağrılır ve statik sınıf programınızı bulunduğu uygulama etki alanı için kullanım ömrünü bellekte kalır.</span><span class="sxs-lookup"><span data-stu-id="99c3b-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99c3b-114">Kendisini oluşturulması için yalnızca bir örneğine izin veren bir statik olmayan sınıf oluşturmak için bkz: [uygulama Singleton C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span><span class="sxs-lookup"><span data-stu-id="99c3b-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span></span>  
  
 <span data-ttu-id="99c3b-115">Aşağıdaki listede statik sınıf ana özelliklerini sağlar:</span><span class="sxs-lookup"><span data-stu-id="99c3b-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="99c3b-116">Yalnızca statik üyeler içeriyor.</span><span class="sxs-lookup"><span data-stu-id="99c3b-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="99c3b-117">Örneği oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="99c3b-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="99c3b-118">Korumalı değil.</span><span class="sxs-lookup"><span data-stu-id="99c3b-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="99c3b-119">İçeremez [örnek oluşturucuları](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="99c3b-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="99c3b-120">Bir statik sınıf oluşturma bu nedenle temelde yalnızca statik üyeleri ve bir özel oluşturucu içeren bir sınıf oluşturma ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="99c3b-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="99c3b-121">Özel oluşturucu sınıfı oluşturulmasını engeller.</span><span class="sxs-lookup"><span data-stu-id="99c3b-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="99c3b-122">Statik sınıf kullanmanın avantajı, derleyici hiçbir örnek üyesinin yanlışlıkla eklendiğinden emin olmak için kontrol edebilirsiniz ' dir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="99c3b-123">Derleyici, bu sınıfın örnekleri, oluşturulamıyor garanti.</span><span class="sxs-lookup"><span data-stu-id="99c3b-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="99c3b-124">Statik sınıflar mühürlendi ve bu nedenle devralındı.</span><span class="sxs-lookup"><span data-stu-id="99c3b-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="99c3b-125">Dışında herhangi bir sınıftan devralınan olamaz <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="99c3b-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="99c3b-126">Statik sınıflar örnek oluşturucu içeremez; Bununla birlikte, bunlar statik Oluşturucu içerebilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="99c3b-127">Sınıf Önemsiz olmayan başlatma gerektiren statik üyeler içeriyorsa, statik olmayan sınıfları ayrıca statik Oluşturucu tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="99c3b-128">Daha fazla bilgi için bkz: [statik oluşturucular](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="99c3b-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c3b-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="99c3b-129">Example</span></span>  
 <span data-ttu-id="99c3b-130">Burada, fahrenhayt derece ve derece Fahrenhayt sıcaklık Dönüştür iki yöntemleri içeren bir statik sınıf örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="99c3b-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 [!code-csharp[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a><span data-ttu-id="99c3b-131">Statik Üyeler</span><span class="sxs-lookup"><span data-stu-id="99c3b-131">Static Members</span></span>  
 <span data-ttu-id="99c3b-132">Statik olmayan sınıfı statik yöntemler, alanları, özellikleri veya olayları içerebilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-132">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="99c3b-133">Statik üye bile sınıfının hiçbir örneği oluşturulduğunda bir sınıf üzerinde çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-133">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="99c3b-134">Statik üye sınıfı adı, örnek adı her zaman erişilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-134">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="99c3b-135">Kaç tane sınıfın örnekleri, oluşturulan bağımsız olarak yalnızca bir kopyasını statik bir üyenin bulunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="99c3b-135">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="99c3b-136">Statik yöntemler ve Özellikler statik olmayan alanlar ve kendilerini kapsayan türle olayları erişemez ve açıkça bir yöntem parametresinde geçirilen sürece herhangi bir nesnenin bir örnek değişkeni erişemiyor.</span><span class="sxs-lookup"><span data-stu-id="99c3b-136">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="99c3b-137">Statik olarak sınıfının tümüne bildirmek üzere daha bazı statik üyeleri olan bir statik olmayan sınıfı bildirmek için daha genel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="99c3b-137">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="99c3b-138">Statik alanları iki yaygın kullanımları şunlardır: örneği nesneleri sayısını tutmak için ya da tüm örnekler arasında paylaşılan bir değeri depolamak için.</span><span class="sxs-lookup"><span data-stu-id="99c3b-138">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="99c3b-139">Statik yöntemler aşırı ancak sınıfı ve değil sınıfın örneklerini ait olduğundan, geçersiz.</span><span class="sxs-lookup"><span data-stu-id="99c3b-139">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="99c3b-140">Bir alan olarak bildirilemez rağmen `static const`, [const](../../../csharp/language-reference/keywords/const.md) alandır davranışını içinde temelde statik.</span><span class="sxs-lookup"><span data-stu-id="99c3b-140">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="99c3b-141">Türünün örnekleri için türüne ait.</span><span class="sxs-lookup"><span data-stu-id="99c3b-141">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="99c3b-142">Bu nedenle, const alanları aynı kullanarak erişilebilir `ClassName.MemberName` statik alanlar için kullanılan gösterimi.</span><span class="sxs-lookup"><span data-stu-id="99c3b-142">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="99c3b-143">Hiçbir nesne örneği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-143">No object instance is required.</span></span>  
  
 <span data-ttu-id="99c3b-144">C# statik yerel değişkenler (yöntemi kapsamda bildirilen değişkenler) desteklemez.</span><span class="sxs-lookup"><span data-stu-id="99c3b-144">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="99c3b-145">Kullanarak statik sınıf üyeleri bildirme `static` anahtar sözcüğü dönüş türü üyesinin aşağıdaki örnekte gösterildiği gibi önce:</span><span class="sxs-lookup"><span data-stu-id="99c3b-145">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 <span data-ttu-id="99c3b-146">Statik üyeler statik üyenin ilk kez ve statik Oluşturucusu önce erişmeden önce başlatılır varsa, adı verilir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-146">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="99c3b-147">Statik sınıf üyesine erişme için sınıfı adı değişken adı yerine üye konumunu belirtmek için aşağıdaki örnekte gösterildiği gibi kullanın:</span><span class="sxs-lookup"><span data-stu-id="99c3b-147">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 <span data-ttu-id="99c3b-148">Sınıfınızda statik alanları içeriyorsa, sınıf yüklendiğinde, bunları başlatır statik Oluşturucu sağlayın.</span><span class="sxs-lookup"><span data-stu-id="99c3b-148">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="99c3b-149">Bir örnek yöntemine yapılan bir çağrı davranırken bir statik yöntem çağrısı bir çağrı yönergesi Microsoft Ara dili (MSIL) oluşturur. bir `callvirt` null bir nesne başvuran için ve ayrıca denetleyen yönerge.</span><span class="sxs-lookup"><span data-stu-id="99c3b-149">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="99c3b-150">Bununla birlikte, çoğu zaman iki arasındaki performans farkının önemli değildir.</span><span class="sxs-lookup"><span data-stu-id="99c3b-150">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="99c3b-151">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="99c3b-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99c3b-152">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="99c3b-152">See Also</span></span>  
 [<span data-ttu-id="99c3b-153">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="99c3b-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="99c3b-154">statik</span><span class="sxs-lookup"><span data-stu-id="99c3b-154">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="99c3b-155">Sınıfları</span><span class="sxs-lookup"><span data-stu-id="99c3b-155">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="99c3b-156">sınıfı</span><span class="sxs-lookup"><span data-stu-id="99c3b-156">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="99c3b-157">Statik oluşturucular</span><span class="sxs-lookup"><span data-stu-id="99c3b-157">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
 [<span data-ttu-id="99c3b-158">Örnek oluşturucuları</span><span class="sxs-lookup"><span data-stu-id="99c3b-158">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)