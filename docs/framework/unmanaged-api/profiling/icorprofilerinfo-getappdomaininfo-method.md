---
title: "ICorProfilerInfo::GetAppDomainInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAppDomainInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type: apiref
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c31d3c61a868bf741213f6e505d91524cc925207
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="c54bb-102">ICorProfilerInfo::GetAppDomainInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="c54bb-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>
<span data-ttu-id="c54bb-103">Acepta un identificador de dominio de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-103">Accepts an application domain ID.</span></span> <span data-ttu-id="c54bb-104">Devuelve un nombre de dominio de una aplicación y el identificador del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c54bb-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c54bb-105">Syntax</span></span>  
  
```  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c54bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c54bb-106">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c54bb-107">[in] Identificador de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c54bb-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="c54bb-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c54bb-109">[out] Puntero a la longitud total de caracteres del nombre de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="c54bb-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="c54bb-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="c54bb-111">Con la devolución del método, `szName` contendrá el nombre total o parcial del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="c54bb-112">[out] Puntero al identificador del proceso que contiene el dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c54bb-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c54bb-113">Remarks</span></span>  
 <span data-ttu-id="c54bb-114">Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c54bb-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="c54bb-115">Para ello, compare el valor que señala `pcchName` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="c54bb-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c54bb-116">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="c54bb-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="c54bb-117">También puede llamar primero a `GetAppDomainInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="c54bb-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c54bb-118">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="c54bb-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c54bb-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c54bb-119">Requirements</span></span>  
 <span data-ttu-id="c54bb-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c54bb-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c54bb-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c54bb-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c54bb-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c54bb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c54bb-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c54bb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c54bb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c54bb-124">See Also</span></span>  
 [<span data-ttu-id="c54bb-125">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c54bb-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c54bb-126">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c54bb-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c54bb-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c54bb-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)