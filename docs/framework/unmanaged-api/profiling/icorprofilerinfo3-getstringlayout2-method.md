---
title: "ICorProfilerInfo3::GetStringLayout2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetStringLayout2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de89776c6208ec7e3434fa747057edbf818ec013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="10034-102">ICorProfilerInfo3::GetStringLayout2 (Método)</span><span class="sxs-lookup"><span data-stu-id="10034-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="10034-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="10034-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="10034-104">Este método reemplaza a la [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="10034-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10034-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10034-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10034-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10034-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="10034-107">[out] Un puntero al desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="10034-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="10034-108">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="10034-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="10034-109">[out] Un puntero para el desplazamiento del búfer, relativo a la `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="10034-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10034-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10034-110">Remarks</span></span>  
 <span data-ttu-id="10034-111">Las cadenas pueden o no pueden ser terminada en null.</span><span class="sxs-lookup"><span data-stu-id="10034-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10034-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10034-112">Requirements</span></span>  
 <span data-ttu-id="10034-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10034-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10034-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10034-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10034-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10034-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10034-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10034-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10034-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="10034-117">See Also</span></span>  
 [<span data-ttu-id="10034-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10034-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="10034-119">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="10034-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)