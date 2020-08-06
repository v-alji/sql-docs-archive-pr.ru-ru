---
title: Удалите схему CDC, если планируется включить систему отслеживания измененных данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- cdc schema
- change data capture
ms.assetid: 6a84aa25-0f31-4be3-b2dd-4f249b8254ae
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: abdb33fa3d1ff022a65ed569f19d48bcf4468501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666364"
---
# <a name="remove-the-cdc-schema-if-you-plan-to-enable-change-data-capture"></a><span data-ttu-id="7bcbe-102">Удаление схемы cdc, если планируется ввести в действие систему отслеживания измененных данных</span><span class="sxs-lookup"><span data-stu-id="7bcbe-102">Remove the cdc schema if you plan to enable change data capture</span></span>
  <span data-ttu-id="7bcbe-103">База данных уже содержит схему cdc.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-103">A database already contains a cdc schema.</span></span> <span data-ttu-id="7bcbe-104">Если планируется разрешить использование системы отслеживания измененных данных после обновления, необходимо вначале удалить эту схему cdc.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-104">If you plan to enable change data capture after upgrade, you must first drop this cdc schema.</span></span> <span data-ttu-id="7bcbe-105">Если в базе данных включено применение системы отслеживания измененных данных, то в [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] создается новая схема с именем cdc.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-105">When you enable a database for change data capture, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create a new schema named cdc.</span></span>  
  
  
