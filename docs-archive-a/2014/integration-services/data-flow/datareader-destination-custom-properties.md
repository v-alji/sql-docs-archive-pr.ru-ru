---
title: Пользовательские свойства назначения "Модуль чтения данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665038"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="b2935-102">Пользовательские свойства назначения «Модуль чтения данных»</span><span class="sxs-lookup"><span data-stu-id="b2935-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="b2935-103">Назначение «Модуль чтения данных» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="b2935-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="b2935-104">В следующей таблице описаны пользовательские свойства назначения «Модуль чтения данных».</span><span class="sxs-lookup"><span data-stu-id="b2935-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="b2935-105">Все свойства, за исключением `DataReader`, доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="b2935-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="b2935-106">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="b2935-106">Property name</span></span>|<span data-ttu-id="b2935-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b2935-107">Data Type</span></span>|<span data-ttu-id="b2935-108">Description</span><span class="sxs-lookup"><span data-stu-id="b2935-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="b2935-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="b2935-109">DataReader</span></span>|<span data-ttu-id="b2935-110">String</span><span class="sxs-lookup"><span data-stu-id="b2935-110">String</span></span>|<span data-ttu-id="b2935-111">Имя класса назначения «Модуль чтения данных».</span><span class="sxs-lookup"><span data-stu-id="b2935-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="b2935-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="b2935-112">FailOnTimeout</span></span>|<span data-ttu-id="b2935-113">Логическое</span><span class="sxs-lookup"><span data-stu-id="b2935-113">Boolean</span></span>|<span data-ttu-id="b2935-114">Показывает, завершать ли работу с ошибкой, когда истекает время ожидания чтения (`ReadTimeout`).</span><span class="sxs-lookup"><span data-stu-id="b2935-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="b2935-115">Это свойство имеет значение по умолчанию **False**.</span><span class="sxs-lookup"><span data-stu-id="b2935-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="b2935-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="b2935-116">ReadTimeout</span></span>|<span data-ttu-id="b2935-117">Целое число</span><span class="sxs-lookup"><span data-stu-id="b2935-117">Integer</span></span>|<span data-ttu-id="b2935-118">Количество миллисекунд до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="b2935-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="b2935-119">По умолчанию для этого свойства устанавливается значение 30000 (30 секунд).</span><span class="sxs-lookup"><span data-stu-id="b2935-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="b2935-120">Ввод и входные столбцы назначения «Модуль чтения данных» не обладают пользовательскими свойствами.</span><span class="sxs-lookup"><span data-stu-id="b2935-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="b2935-121">Дополнительные сведения см. в статье [DataReader Destination](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b2935-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2935-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2935-122">See Also</span></span>  
 [<span data-ttu-id="b2935-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="b2935-123">Common Properties</span></span>](../common-properties.md)  
  
  
