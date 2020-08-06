---
title: Свойства сервера (страница "Прочие параметры сервера") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665114"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="1e75e-102">Свойства сервера (страница «Прочие установки сервера»)</span><span class="sxs-lookup"><span data-stu-id="1e75e-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="1e75e-103">Эта страница используется для просмотра или изменения установок сервера.</span><span class="sxs-lookup"><span data-stu-id="1e75e-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e75e-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e75e-104">Options</span></span>  
 <span data-ttu-id="1e75e-105">**Язык по умолчанию для пользователей**</span><span class="sxs-lookup"><span data-stu-id="1e75e-105">**Default language for users**</span></span>  
 <span data-ttu-id="1e75e-106">Указывает язык, используемый по умолчанию для всех созданных имен входа.</span><span class="sxs-lookup"><span data-stu-id="1e75e-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="1e75e-107">**Разрешить триггерам вызывать срабатывание других триггеров**</span><span class="sxs-lookup"><span data-stu-id="1e75e-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="1e75e-108">Управляет возможностью триггера выполнить действие, вызывающее срабатывание других триггеров.</span><span class="sxs-lookup"><span data-stu-id="1e75e-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="1e75e-109">Если этот флажок не установлен, триггеры не могут срабатывать от других триггеров.</span><span class="sxs-lookup"><span data-stu-id="1e75e-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="1e75e-110">Если этот флажок установлен, срабатывание триггеров может вызываться другими триггерами более чем на 32 уровнях.</span><span class="sxs-lookup"><span data-stu-id="1e75e-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="1e75e-111">**Использовать регулятор запросов для сокращения времени их выполнения**</span><span class="sxs-lookup"><span data-stu-id="1e75e-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="1e75e-112">Определяет максимальное значение времени, в течение которого может выполняться запрос.</span><span class="sxs-lookup"><span data-stu-id="1e75e-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="1e75e-113">Стоимость запроса соответствует предполагаемому времени в секундах, которое требуется для выполнения запроса на определенной конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e75e-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="1e75e-114">По умолчанию регулятор запросов отключен и для всех запросов имеется разрешение на выполнение.</span><span class="sxs-lookup"><span data-stu-id="1e75e-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="1e75e-115">При выборе этого параметра в расположенное внизу текстовое поле необходимо ввести временное ограничение.</span><span class="sxs-lookup"><span data-stu-id="1e75e-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="1e75e-116">Если задать значение больше нуля, регулятор запросов запрещает выполнение всех запросов, оценочная стоимость которых превышает это значение.</span><span class="sxs-lookup"><span data-stu-id="1e75e-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="1e75e-117">**Интерпретация двузначного числа для года в диапазоне**</span><span class="sxs-lookup"><span data-stu-id="1e75e-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="1e75e-118">Определяет столетний диапазон дат для интерпретации двузначных чисел, обозначающих год.</span><span class="sxs-lookup"><span data-stu-id="1e75e-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1e75e-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет интерпретировать двухзначное значение даты как год, заканчивающийся этими цифрами и находящийся в указанном диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="1e75e-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="1e75e-120">Введите в правое поле последние две цифры года.</span><span class="sxs-lookup"><span data-stu-id="1e75e-120">Set the right box with the ending year.</span></span> <span data-ttu-id="1e75e-121">При сохранении года [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически заполняет левое поле начальными цифрами года.</span><span class="sxs-lookup"><span data-stu-id="1e75e-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="1e75e-122">**Настроенные значения**</span><span class="sxs-lookup"><span data-stu-id="1e75e-122">**Configured Values**</span></span>  
 <span data-ttu-id="1e75e-123">Отображает настроенные значения для параметров на этой панели.</span><span class="sxs-lookup"><span data-stu-id="1e75e-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="1e75e-124">В случае изменения этих значений выберите пункт **Текущие значения** и посмотрите, вступили ли в силу внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="1e75e-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="1e75e-125">Если изменения не вступили в силу, значит, экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вначале должен быть перезапущен.</span><span class="sxs-lookup"><span data-stu-id="1e75e-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="1e75e-126">**Текущие значения**</span><span class="sxs-lookup"><span data-stu-id="1e75e-126">**Running Values**</span></span>  
 <span data-ttu-id="1e75e-127">Просмотр текущих значений для параметров на этой панели.</span><span class="sxs-lookup"><span data-stu-id="1e75e-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="1e75e-128">Эти значения доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1e75e-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e75e-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e75e-129">See Also</span></span>  
 [<span data-ttu-id="1e75e-130">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e75e-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
