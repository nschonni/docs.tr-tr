---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a><span data-ttu-id="63d75-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="63d75-102">/libpath</span></span>
<span data-ttu-id="63d75-103">Başvurulan derlemelerin konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="63d75-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d75-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="63d75-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="63d75-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="63d75-105">Arguments</span></span>  
  
|<span data-ttu-id="63d75-106">Terim</span><span class="sxs-lookup"><span data-stu-id="63d75-106">Term</span></span>|<span data-ttu-id="63d75-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="63d75-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="63d75-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="63d75-108">Required.</span></span> <span data-ttu-id="63d75-109">Başvurulan bir derleme IF Bakılacak derleme için dizinler noktalı virgülle ayrılmış listesi bulunamadı ya da geçerli çalışma dizini (içinden, derleyiciyi çağırdığınız dizin) veya ortak dil çalışma zamanı 's sistem dizini.</span><span class="sxs-lookup"><span data-stu-id="63d75-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="63d75-110">Dizin adı boşluk içeriyorsa adı tırnak işaretleri içine alın ("").</span><span class="sxs-lookup"><span data-stu-id="63d75-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63d75-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="63d75-111">Remarks</span></span>  
 <span data-ttu-id="63d75-112">`/libpath` Seçeneği tarafından başvurulan derlemelerin konumunu belirtir [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) seçeneği.</span><span class="sxs-lookup"><span data-stu-id="63d75-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="63d75-113">Aşağıdaki sırayla tam olarak nitelenmiş değil derleme başvurularını derleyici arar:</span><span class="sxs-lookup"><span data-stu-id="63d75-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="63d75-114">Geçerli çalışma dizini.</span><span class="sxs-lookup"><span data-stu-id="63d75-114">Current working directory.</span></span> <span data-ttu-id="63d75-115">Bu, derleyicinin çağırıldığı dizindir.</span><span class="sxs-lookup"><span data-stu-id="63d75-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="63d75-116">Ortak dil çalışma zamanı sistem dizini.</span><span class="sxs-lookup"><span data-stu-id="63d75-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="63d75-117">Tarafından belirtilen dizin `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="63d75-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="63d75-118">LIB ortam değişkeni tarafından belirtilen dizin.</span><span class="sxs-lookup"><span data-stu-id="63d75-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="63d75-119">`/libpath` Seçenektir eklenebilir; belirten daha çok kez herhangi bir önceki değeri ekler.</span><span class="sxs-lookup"><span data-stu-id="63d75-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="63d75-120">Kullanım `/reference` bir derleme başvurusu belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="63d75-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="63d75-121">Tümleşik geliştirme ortamı/Libpath Visual Studio'da ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="63d75-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="63d75-122">1.  Seçili bir projeyi **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="63d75-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="63d75-123">Üzerinde **proje** menüsünde tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="63d75-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="63d75-124">Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="63d75-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="63d75-125">2.  Tıklatın **başvuruları** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="63d75-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="63d75-126">3.  Tıklatın **başvuru yolları...**  düğmesi.</span><span class="sxs-lookup"><span data-stu-id="63d75-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="63d75-127">4.  İçinde **başvuru yollarını** iletişim kutusunda, dizin adı girin **klasörü:** kutusu.</span><span class="sxs-lookup"><span data-stu-id="63d75-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="63d75-128">5.  Tıklatın **klasörü Ekle**.</span><span class="sxs-lookup"><span data-stu-id="63d75-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="63d75-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="63d75-129">Example</span></span>  
 <span data-ttu-id="63d75-130">Aşağıdaki kod derlerken `T2.vb` bir .exe dosyası oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="63d75-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="63d75-131">Derleyici derleme başvuruları için çalışma dizini, C: sürücüsünün kök dizinindeki ve C: sürücüsüne yeni derlemeleri dizinini arar.</span><span class="sxs-lookup"><span data-stu-id="63d75-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="63d75-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="63d75-132">See Also</span></span>  
 [<span data-ttu-id="63d75-133">Derlemeler ve Genel Derleme Önbelleği</span><span class="sxs-lookup"><span data-stu-id="63d75-133">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="63d75-134">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="63d75-134">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="63d75-135">Örnek derleme komut satırları</span><span class="sxs-lookup"><span data-stu-id="63d75-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)