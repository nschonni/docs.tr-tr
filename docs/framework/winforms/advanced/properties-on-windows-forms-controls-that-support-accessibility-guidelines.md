---
title: "Windows Forms Denetimlerinde Erişilebilirlik Yönergelerini Destekleyen Özellikler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ca18b35b90b028054e68a0a14fecc819a6c20b9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="9f1c0-102">Windows Forms Denetimlerinde Erişilebilirlik Yönergelerini Destekleyen Özellikler</span><span class="sxs-lookup"><span data-stu-id="9f1c0-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="9f1c0-103">Windows Forms için standart araç çubuğu denetimleri klavye odağını gösterme ve ekran öğeleri gösterme dahil olmak üzere erişilebilirlik yönergelerini çoğunu destekler.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="9f1c0-104">Erişilebilirlik için planlama</span><span class="sxs-lookup"><span data-stu-id="9f1c0-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="9f1c0-105">Denetimleri özellikler aşağıdaki tabloda gösterildiği gibi diğer erişilebilirlik yönergelerini desteklemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="9f1c0-106">Ayrıca, menüler program özellikleri erişim sağlamak için kullanmalısınız.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="9f1c0-107">Denetim özelliği</span><span class="sxs-lookup"><span data-stu-id="9f1c0-107">Control Property</span></span>|<span data-ttu-id="9f1c0-108">Erişilebilirlik konuları</span><span class="sxs-lookup"><span data-stu-id="9f1c0-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="9f1c0-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="9f1c0-109">AccessibleDescription</span></span>|<span data-ttu-id="9f1c0-110">Açıklama, ekran okuyucular gibi erişilebilirlik Yardımcıları bildirilir.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="9f1c0-111">Erişilebilirlik yardımları özelleştirilmiş programlardır ve engelli kişilere yardımcı aygıtları bilgisayarlar daha etkili bir şekilde kullanın.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="9f1c0-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="9f1c0-112">AccessibleName</span></span>|<span data-ttu-id="9f1c0-113">Erişilebilirlik yardımları bildirilecek adı.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="9f1c0-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="9f1c0-114">AccessibleRole</span></span>|<span data-ttu-id="9f1c0-115">Kullanıcı arabirimi öğesinde kullanımını açıklar.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="9f1c0-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="9f1c0-116">TabIndex</span></span>|<span data-ttu-id="9f1c0-117">Formun duyarlı bir gezinme yol oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="9f1c0-118">Metin kutuları, hemen sekme sırası önünde yer bunların ilişkili etiketi olması gibi iç etiketleri olmadan denetimler önemlidir.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="9f1c0-119">Metin</span><span class="sxs-lookup"><span data-stu-id="9f1c0-119">Text</span></span>|<span data-ttu-id="9f1c0-120">Erişim tuşları oluşturma için "&" karakterini kullanın.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="9f1c0-121">Erişim tuşlarını kullanarak özellikleri belgelenen Klavye erişimi sağlama bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="9f1c0-122">Yazı tipi boyutu</span><span class="sxs-lookup"><span data-stu-id="9f1c0-122">Font Size</span></span>|<span data-ttu-id="9f1c0-123">Yazı tipi boyutu ayarlanabilir değilse, sonra da 10 noktası ya da daha büyük ayarlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="9f1c0-124">Forma bundan sonra eklenen tüm denetimler, formun yazı tipi boyutunu ayarladıktan sonra aynı boyuta sahip olur.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="9f1c0-125">ForeColor</span><span class="sxs-lookup"><span data-stu-id="9f1c0-125">Forecolor</span></span>|<span data-ttu-id="9f1c0-126">Bu özellik varsayılan olarak ayarlanırsa, kullanıcının renk tercihlerini formda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="9f1c0-127">Arka plan rengi</span><span class="sxs-lookup"><span data-stu-id="9f1c0-127">Backcolor</span></span>|<span data-ttu-id="9f1c0-128">Bu özellik varsayılan olarak ayarlanırsa, kullanıcının renk tercihlerini formda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="9f1c0-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="9f1c0-129">BackgroundImage</span></span>|<span data-ttu-id="9f1c0-130">Bu özellik metin daha okunabilir hale için boş bırakın.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f1c0-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9f1c0-131">See Also</span></span>  
 [<span data-ttu-id="9f1c0-132">İzlenecek yol: erişilebilir bir Windows tabanlı uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="9f1c0-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)