---
title: "İş Akışı Hizmetlerini Barındırma Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="6f89d-102">İş Akışı Hizmetlerini Barındırma Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="6f89d-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="6f89d-103">İş akışı hizmetleri yürütmek için barındırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6f89d-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="6f89d-104"><xref:System.ServiceModel.WorkflowServiceHost> (İş akışları barındırılması için Mesajlaşma kullanmak için gerekli olmasa da) destekleyen birden çok örneği, yapılandırma ve WCF ileti Giden kutusu iş akışı ana bilgisayardır.</span><span class="sxs-lookup"><span data-stu-id="6f89d-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="6f89d-105">Ayrıca Kalıcılık, izleme ve bir dizi hizmet davranışları örneği denetimi ile tümleştirilir.</span><span class="sxs-lookup"><span data-stu-id="6f89d-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="6f89d-106">WCF'ın ' olduğu gibi <xref:System.ServiceModel.ServiceHost>, <xref:System.ServiceModel.WorkflowServiceHost> herhangi bir yönetilen .NET uygulamasında kendi kendini barındıran veya web (.xamlx dosyası olarak) IIS'de barındırılan / OLUŞTU.</span><span class="sxs-lookup"><span data-stu-id="6f89d-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="6f89d-107">Bu bölümdeki konular, bir iş akışı hizmeti barındırma açıklar.</span><span class="sxs-lookup"><span data-stu-id="6f89d-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f89d-108">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="6f89d-108">In This Section</span></span>  
 [<span data-ttu-id="6f89d-109">İş akışı hizmetlerini barındırma</span><span class="sxs-lookup"><span data-stu-id="6f89d-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="6f89d-110">İş akışı hizmetlerini barındırma açıklar.</span><span class="sxs-lookup"><span data-stu-id="6f89d-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="6f89d-111">İş akışı hizmeti konağı dahili bileşenleri</span><span class="sxs-lookup"><span data-stu-id="6f89d-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="6f89d-112">Açıklar nasıl <xref:System.ServiceModel.WorkflowServiceHost> gelen iletileri işler.</span><span class="sxs-lookup"><span data-stu-id="6f89d-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="6f89d-113">İş akışı hizmeti konak genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="6f89d-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="6f89d-114">İş akışı hizmeti ana bilgisayarı işlevselliğini genişletmek açıklar.</span><span class="sxs-lookup"><span data-stu-id="6f89d-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="6f89d-115">İş akışı denetim uç noktası</span><span class="sxs-lookup"><span data-stu-id="6f89d-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="6f89d-116">İş akışı örnekleri oluşturmanıza olanak tanıyan bir uç nokta tanımlanacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="6f89d-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="6f89d-117">Nasıl yapılır: IIS'de hizmet olmayan iş akışı barındırma</span><span class="sxs-lookup"><span data-stu-id="6f89d-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="6f89d-118">Bir iş akışı hizmeti IIS olmayan bir iş akışı barındırma gösterir.</span><span class="sxs-lookup"><span data-stu-id="6f89d-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="6f89d-119">Nasıl yapılır: Windows Server App Fabric ile iş akışı hizmeti barındırma</span><span class="sxs-lookup"><span data-stu-id="6f89d-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="6f89d-120">Windows Server App Fabric var olan bir iş akışı hizmetinde barındırmak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="6f89d-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="6f89d-121">WorkflowServiceHost yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6f89d-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="6f89d-122">Kalıcılık, izleme, boşta ve işlenmeyen özel durum davranışını denetlemek açıklar.</span><span class="sxs-lookup"><span data-stu-id="6f89d-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6f89d-123">Başvuru</span><span class="sxs-lookup"><span data-stu-id="6f89d-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="6f89d-124">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="6f89d-124">Related Sections</span></span>  
 [<span data-ttu-id="6f89d-125">İş akışı Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="6f89d-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)