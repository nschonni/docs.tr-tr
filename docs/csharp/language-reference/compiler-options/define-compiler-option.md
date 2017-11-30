---
title: "-tanımlama (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4c7e4e646e6796cff6bbfbe05038ff361fa80c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="define-c-compiler-options"></a><span data-ttu-id="2d34b-102">/define (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="2d34b-102">/define (C# Compiler Options)</span></span>
<span data-ttu-id="2d34b-103">**/ Define** seçeneği tanımlar `name` programınızın tüm kaynak kodda bir simge dosyaları olarak.</span><span class="sxs-lookup"><span data-stu-id="2d34b-103">The **/define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d34b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2d34b-104">Syntax</span></span>  
  
```console  
/define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d34b-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2d34b-105">Arguments</span></span>  
 <span data-ttu-id="2d34b-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="2d34b-106">`name`, `name2`</span></span>  
 <span data-ttu-id="2d34b-107">Tanımlamak istediğiniz bir veya daha fazla simgeleri adı.</span><span class="sxs-lookup"><span data-stu-id="2d34b-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d34b-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2d34b-108">Remarks</span></span>  
 <span data-ttu-id="2d34b-109">**/ Define** seçeneğini kullanarak aynı etkiye sahip bir [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) önişlemci yönergesi derleyici seçeneği projedeki tüm dosyalar için etkin olması dışında.</span><span class="sxs-lookup"><span data-stu-id="2d34b-109">The **/define** option has the same effect as using a [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="2d34b-110">Bir simge, kadar kaynak dosyasında tanımlanmış kalır bir [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) kaynak dosyasını yönergesinde tanımı kaldırır.</span><span class="sxs-lookup"><span data-stu-id="2d34b-110">A symbol remains defined in a source file until an [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="2d34b-111">Kullandığınızda / define seçeneği, bir `#undef` bir dosyada yönergesi diğer kaynak kodu dosyaları projedeki hiçbir etkisi.</span><span class="sxs-lookup"><span data-stu-id="2d34b-111">When you use the /define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="2d34b-112">Bu seçenek ile tarafından oluşturulan simgeleri kullanabilirsiniz [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), ve [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) koşullu kaynak dosyalarını derlemek için.</span><span class="sxs-lookup"><span data-stu-id="2d34b-112">You can use symbols created by this option with [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), and [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="2d34b-113">**/d** kısa biçimi olan **/ define**.</span><span class="sxs-lookup"><span data-stu-id="2d34b-113">**/d** is the short form of **/define**.</span></span>  
  
 <span data-ttu-id="2d34b-114">Birden çok sembolleriyle tanımlayabilirsiniz **/ define** sembol adları ayırmak için noktalı virgül veya nokta kullanarak.</span><span class="sxs-lookup"><span data-stu-id="2d34b-114">You can define multiple symbols with **/define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="2d34b-115">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="2d34b-115">For example:</span></span>  
  
```console  
/define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="2d34b-116">C# Derleyici kendisini bir simge veya kaynak kodunuzda kullanabilirsiniz makroları tanımlar; Tüm simge tanımlarının kullanıcı tanımlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2d34b-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d34b-117">C# `#define` C++ gibi dilleri olduğu gibi bir değer verilmesi bir simge izin vermiyor.</span><span class="sxs-lookup"><span data-stu-id="2d34b-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="2d34b-118">Örneğin, `#define` makro oluşturmak veya sabit tanımlamak için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="2d34b-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="2d34b-119">Bir sabit tanımlamanız gerekiyorsa kullanın bir `enum` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="2d34b-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="2d34b-120">C++ tarzı makro oluşturmak istiyorsanız, genel türler gibi Alternatiflere göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="2d34b-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="2d34b-121">Makrolar hataya yatkın olduğundan, C# kullanımlarını izin vermez ancak daha güvenli alternatifler sunar.</span><span class="sxs-lookup"><span data-stu-id="2d34b-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2d34b-122">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="2d34b-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="2d34b-123">Projenin açmak **özellikleri** sayfası.</span><span class="sxs-lookup"><span data-stu-id="2d34b-123">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="2d34b-124">Üzerinde **yapı** sekmesinde, tanımlanması için simge türü **koşullu derleme simgeleri** kutusu.</span><span class="sxs-lookup"><span data-stu-id="2d34b-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="2d34b-125">Örneğin, aşağıdaki kod örneği kullanıyorsanız, yalnızca yazın `xx` metin kutusuna.</span><span class="sxs-lookup"><span data-stu-id="2d34b-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="2d34b-126">Bu derleyici seçeneği programlı olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d34b-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d34b-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="2d34b-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d34b-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2d34b-128">See Also</span></span>  
 [<span data-ttu-id="2d34b-129">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="2d34b-129">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="2d34b-130">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="2d34b-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)