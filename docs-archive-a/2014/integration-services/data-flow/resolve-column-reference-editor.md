---
title: Редактор разрешения ссылок на столбцы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665036"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="c629e-102">Редактор разрешения ссылок на столбцы</span><span class="sxs-lookup"><span data-stu-id="c629e-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="c629e-103">Если входной путь отсоединен или если в нем присутствуют несопоставленные столбцы, напротив соответствующего пути данных будет отображен значок ошибки.</span><span class="sxs-lookup"><span data-stu-id="c629e-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="c629e-104">Чтобы упростить разрешение ошибок ссылок на столбцы, новый редактор разрешения ссылок позволяет связывать несопоставленные входные и выходные столбцы для всех путей в дереве выполнения.</span><span class="sxs-lookup"><span data-stu-id="c629e-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="c629e-105">Редактор разрешения ссылок также выделяет пути, чтобы указать, какие из них разрешаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c629e-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c629e-106">Теперь возможно изменить компонент даже в случае, если путь входа отключен.</span><span class="sxs-lookup"><span data-stu-id="c629e-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="c629e-107">Если после того, как все ссылки на столбцы были разрешены, если ошибок пути данных больше не осталось, значки ошибок не будут отображаться напротив путей данных.</span><span class="sxs-lookup"><span data-stu-id="c629e-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c629e-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c629e-108">Options</span></span>  
 <span data-ttu-id="c629e-109">Несопоставленные выходные столбцы (источник):</span><span class="sxs-lookup"><span data-stu-id="c629e-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="c629e-110">Столбцы из восходящего пути, которые в данный момент не сопоставлены</span><span class="sxs-lookup"><span data-stu-id="c629e-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="c629e-111">Сопоставленные столбцы (источник):</span><span class="sxs-lookup"><span data-stu-id="c629e-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="c629e-112">Столбцы из восходящего пути, которые сопоставлены со столбцами из нисходящего пути</span><span class="sxs-lookup"><span data-stu-id="c629e-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="c629e-113">Сопоставленные столбцы (назначение):</span><span class="sxs-lookup"><span data-stu-id="c629e-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="c629e-114">Столбцы из восходящего пути, которые сопоставлены со столбцами из нисходящего пути</span><span class="sxs-lookup"><span data-stu-id="c629e-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="c629e-115">Несопоставленные входные столбцы (назначение):</span><span class="sxs-lookup"><span data-stu-id="c629e-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="c629e-116">Столбцы из нисходящего пути, которые в данный момент не сопоставлены</span><span class="sxs-lookup"><span data-stu-id="c629e-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="c629e-117">Удалить несопоставленные входные столбцы</span><span class="sxs-lookup"><span data-stu-id="c629e-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="c629e-118">Установите флажок «Удалить несопоставленные входные столбцы», чтобы игнорировать несопоставленные столбцы в назначении пути данных.</span><span class="sxs-lookup"><span data-stu-id="c629e-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="c629e-119">При нажатии кнопки «Просмотр изменений» будет отображен список изменений, которые будут внесены при нажатии кнопки «ОК».</span><span class="sxs-lookup"><span data-stu-id="c629e-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  
