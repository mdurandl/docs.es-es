---
title: "Icorprofilerinfo7:: Applymetadata (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorProfilerInfo7.ApplyMetaData
api_location: mscorwks.dll
api_type: COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3724555df58392e5ab59ccb4f52dd2de860b8d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="bcd9e-102">Icorprofilerinfo7:: Applymetadata (método)</span><span class="sxs-lookup"><span data-stu-id="bcd9e-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="bcd9e-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="bcd9e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="bcd9e-104">Se aplica a los metadatos recién definidos por el `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd9e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcd9e-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcd9e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bcd9e-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="bcd9e-107">[in] El identificador del módulo cuyos metadatos se cambió.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd9e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bcd9e-108">Remarks</span></span>  
 <span data-ttu-id="bcd9e-109">Si se realizan cambios en los metadatos después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada, debe llamar a este método antes de usar los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="bcd9e-110">`ApplyMetaData`solo admite la adición de los siguientes tipos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="bcd9e-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="bcd9e-111">`AssemblyRef`registros, lo que se crean mediante una llamada a la [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="bcd9e-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="bcd9e-112">.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-112">method.</span></span>  
  
-   <span data-ttu-id="bcd9e-113">`TypeRef`registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="bcd9e-114">`TypeSpec`registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="bcd9e-115">`MemberRef`registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="bcd9e-116">`MemberSpec`registros, lo que se crean mediante una llamada a la [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="bcd9e-117">`UserString`registros, lo que se crean mediante una llamada a la [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bcd9e-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd9e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcd9e-118">Requirements</span></span>  
 <span data-ttu-id="bcd9e-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd9e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd9e-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcd9e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcd9e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd9e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd9e-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd9e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd9e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcd9e-123">See Also</span></span>  
 [<span data-ttu-id="bcd9e-124">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="bcd9e-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)