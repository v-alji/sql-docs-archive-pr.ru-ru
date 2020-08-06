---
title: Тип установки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 0420c555-7a3b-42b9-8651-0b4f5bcb0008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bab1b6c912dce64d1269fd79348a2b0b85f7f670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730050"
---
# <a name="installation-type"></a><span data-ttu-id="44c2c-102">Тип установки</span><span class="sxs-lookup"><span data-stu-id="44c2c-102">Installation Type</span></span>
  <span data-ttu-id="44c2c-103">На странице «Тип установки» мастера установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] укажите, следует ли установить новый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или добавить компоненты в существующий.</span><span class="sxs-lookup"><span data-stu-id="44c2c-103">Use the Installation Type page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify whether to install a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or add features to an existing instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="44c2c-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="44c2c-104">Options</span></span>  
 <span data-ttu-id="44c2c-105">Установите переключатель в требуемое положение:</span><span class="sxs-lookup"><span data-stu-id="44c2c-105">Select the radio button that specifies your choice:</span></span>  
  
-   <span data-ttu-id="44c2c-106">установить новый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44c2c-106">Perform a new installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="44c2c-107">добавить компоненты в существующий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c2c-107">Add features to an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
     <span data-ttu-id="44c2c-108">При выборе параметра добавления компонентов в существующий экземпляр, в раскрывающемся списке выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для обновления.</span><span class="sxs-lookup"><span data-stu-id="44c2c-108">If you select the option to add features to an existing instance, use the drop-down list to select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to update.</span></span>  
  
 <span data-ttu-id="44c2c-109">Вы можете добавить только функции, поддерживаемые SysPrep, [!INCLUDE[ssDE](../../includes/ssde-md.md)] и [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в подготовленный образ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44c2c-109">You can only add the SysPrep supported features-[!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-to a prepared image of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="44c2c-110">Другие функции, не поддерживаемые SysPrep, могут быть добавлены только после завершения подготовленного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="44c2c-110">Other features that are not supported by SysPrep can be added after the prepared instance is completed.</span></span>  
  
 <span data-ttu-id="44c2c-111">**Примечание.** После установки экземпляра отказоустойчивого кластера добавить в него компоненты невозможно.</span><span class="sxs-lookup"><span data-stu-id="44c2c-111">**Note** You cannot add features to a failover cluster instance after it is installed.</span></span> <span data-ttu-id="44c2c-112">Чтобы добавить компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в существующий отказоустойчивый кластер, необходимо установить отдельный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44c2c-112">To add [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features to an existing failover cluster, you must perform a new installation to install a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
