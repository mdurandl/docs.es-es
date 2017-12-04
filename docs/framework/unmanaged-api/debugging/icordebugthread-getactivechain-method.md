---
title: "ICorDebugThread::GetActiveChain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetActiveChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3f104933bc70682a531c0853cfc6eabcd357831
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="817ec-102">ICorDebugThread::GetActiveChain (Método)</span><span class="sxs-lookup"><span data-stu-id="817ec-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="817ec-103">Obtiene un puntero de interfaz a la cadena de pila activa (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="817ec-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="817ec-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="817ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="817ec-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="817ec-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de la pila.</span><span class="sxs-lookup"><span data-stu-id="817ec-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="817ec-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="817ec-107">Remarks</span></span>  
 <span data-ttu-id="817ec-108">El `ppChain` del parámetro es null si no hay ninguna cadena de pila está activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="817ec-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="817ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="817ec-109">Requirements</span></span>  
 <span data-ttu-id="817ec-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="817ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="817ec-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="817ec-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="817ec-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="817ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="817ec-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="817ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>