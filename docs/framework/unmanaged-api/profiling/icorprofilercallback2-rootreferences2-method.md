---
title: "ICorProfilerCallback2::RootReferences2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.RootReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a0b2e23ba586e7a20ed11de6433b2d87cbe7219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="bc190-102">ICorProfilerCallback2::RootReferences2 (Método)</span><span class="sxs-lookup"><span data-stu-id="bc190-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="bc190-103">Notifica al generador de perfiles acerca de las referencias de raíz después de que se ha producido una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bc190-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="bc190-104">Este método es una extensión de la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bc190-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc190-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc190-105">Syntax</span></span>  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc190-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc190-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="bc190-107">[in] El número de elementos de la `rootRefIds`, `rootKinds`, `rootFlags`, y `rootIds` matrices.</span><span class="sxs-lookup"><span data-stu-id="bc190-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="bc190-108">[in] Una matriz de identificadores de objeto, cada uno de los cuales hace referencia a un objeto estático o un objeto en la pila.</span><span class="sxs-lookup"><span data-stu-id="bc190-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="bc190-109">Elementos de la `rootKinds` matriz proporcionan información para clasificar los elementos correspondientes de la `rootRefIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="bc190-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="bc190-110">[in] Una matriz de [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) valores que indican el tipo de la raíz de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bc190-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="bc190-111">[in] Una matriz de [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) valores que describen las propiedades de una raíz de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bc190-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="bc190-112">[in] Una matriz de UINT_PTR valores que señalan a un entero que contiene información adicional sobre la raíz de la colección de elementos no utilizados, dependiendo del valor de la `rootKinds` parámetro.</span><span class="sxs-lookup"><span data-stu-id="bc190-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="bc190-113">Si el tipo de la raíz es una pila, el identificador de la raíz es para la función que contiene la variable.</span><span class="sxs-lookup"><span data-stu-id="bc190-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="bc190-114">Si ese identificador de raíz es 0, la función es una función sin nombre que es interna al CLR.</span><span class="sxs-lookup"><span data-stu-id="bc190-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="bc190-115">Si el tipo de la raíz es un identificador, el identificador de la raíz es para el identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bc190-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="bc190-116">Para los demás tipos de raíz, el identificador es un valor opaco y debe omitirse.</span><span class="sxs-lookup"><span data-stu-id="bc190-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc190-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc190-117">Remarks</span></span>  
 <span data-ttu-id="bc190-118">El `rootRefIds`, `rootKinds`, `rootFlags`, y `rootIds` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="bc190-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="bc190-119">Es decir, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, y `rootIds[i]` hacen referencia a la misma raíz.</span><span class="sxs-lookup"><span data-stu-id="bc190-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="bc190-120">Ambos `RootReferences` y `RootReferences2` se llama para notificar al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="bc190-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="bc190-121">Los generadores de perfiles normalmente implementará un método o el otro, pero no a ambos, porque la información que se pasa en `RootReferences2` es un supraconjunto de la que se pasan en `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="bc190-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="bc190-122">Es posible que las entradas de `rootRefIds` sea cero, lo que implica que la referencia de raíz correspondiente es null y no hace referencia a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="bc190-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="bc190-123">Los identificadores de objeto devuelven por `RootReferences2` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados puede estar en el proceso de mover objetos de direcciones antiguas a nuevas direcciones.</span><span class="sxs-lookup"><span data-stu-id="bc190-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="bc190-124">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="bc190-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="bc190-125">Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) es llama, todos los objetos que se han movido a sus nuevas ubicaciones y se puede inspeccionar con seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc190-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc190-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc190-126">Requirements</span></span>  
 <span data-ttu-id="bc190-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc190-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc190-128">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc190-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc190-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc190-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc190-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc190-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc190-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc190-131">See Also</span></span>  
 [<span data-ttu-id="bc190-132">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc190-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="bc190-133">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc190-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)