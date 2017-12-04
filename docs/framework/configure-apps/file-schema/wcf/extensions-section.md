---
title: "Sección &lt;extensions&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c8106f004a25f1e4547e9629b881e5bf216490
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="b5366-102">Sección &lt;extensions&gt;</span><span class="sxs-lookup"><span data-stu-id="b5366-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="b5366-103">Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="b5366-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="b5366-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b5366-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5366-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5366-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <extensions>  
    <bindingExtensions>  
    </bindingExtensions>  
    <behaviorExtensions>  
    </behaviorExtensions>  
    <bindingElementExtensions>  
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5366-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5366-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b5366-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b5366-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5366-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5366-108">Attributes</span></span>  
 <span data-ttu-id="b5366-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b5366-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5366-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5366-110">Child Elements</span></span>  
  
|<span data-ttu-id="b5366-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5366-111">Element</span></span>|<span data-ttu-id="b5366-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5366-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5366-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="b5366-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="b5366-114">Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b5366-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="b5366-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="b5366-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="b5366-116">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b5366-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="b5366-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="b5366-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="b5366-118">Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="b5366-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="b5366-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="b5366-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="b5366-120">Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="b5366-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5366-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5366-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b5366-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5366-122">Element</span></span>|<span data-ttu-id="b5366-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5366-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5366-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b5366-124">system.ServiceModel</span></span>|<span data-ttu-id="b5366-125">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="b5366-125">The root element of all WCF configuration elements.</span></span>|