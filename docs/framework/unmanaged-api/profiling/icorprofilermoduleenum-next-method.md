---
title: "ICorProfilerModuleEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c20b6970c0df30b75bacf76f52c7610bd4a3a5e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="a11c1-102">ICorProfilerModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a11c1-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="a11c1-103">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a11c1-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a11c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a11c1-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a11c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a11c1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a11c1-106">[in] Número de módulos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="a11c1-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="a11c1-107">[out] Matriz de valores `ModuleID`, cada uno de los cuales representa un módulo recuperado.</span><span class="sxs-lookup"><span data-stu-id="a11c1-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a11c1-108">[out] Puntero al número de elementos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="a11c1-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a11c1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a11c1-109">Return Value</span></span>  
 <span data-ttu-id="a11c1-110">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a11c1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a11c1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a11c1-111">HRESULT</span></span>|<span data-ttu-id="a11c1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a11c1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a11c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a11c1-113">S_OK</span></span>|<span data-ttu-id="a11c1-114">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="a11c1-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="a11c1-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a11c1-115">S_FALSE</span></span>|<span data-ttu-id="a11c1-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="a11c1-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a11c1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a11c1-117">Requirements</span></span>  
 <span data-ttu-id="a11c1-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a11c1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a11c1-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a11c1-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a11c1-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a11c1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a11c1-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a11c1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11c1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a11c1-122">See Also</span></span>  
 [<span data-ttu-id="a11c1-123">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a11c1-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="a11c1-124">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a11c1-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)