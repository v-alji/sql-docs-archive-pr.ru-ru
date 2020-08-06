---
title: Создание и запуск скрипта дополнительного журналирования | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728629"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="a8b53-102">Создание и запуск скрипта дополнительного журналирования</span><span class="sxs-lookup"><span data-stu-id="a8b53-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="a8b53-103">Страница «Настройка таблиц для отслеживания изменений» служит для запуска в базе данных-источнике Oracle скрипта для задания дополнительного журналирования.</span><span class="sxs-lookup"><span data-stu-id="a8b53-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="a8b53-104">**Запуск скриптов дополнительного журналирования**</span><span class="sxs-lookup"><span data-stu-id="a8b53-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="a8b53-105">Нажмите кнопку **Выполнить скрипт** , чтобы запустить скрипт дополнительного журналирования в таблицах, определенных для экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a8b53-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="a8b53-106">Этот скрипт настраивает базу данных Oracle таким образом, что все интересующие столбцы будут записываться в журналы транзакций базы данных при регистрации операций UPDATE для отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="a8b53-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="a8b53-107">Как правило, этот скрипт проверяет и выполняет системный администратор Oracle.</span><span class="sxs-lookup"><span data-stu-id="a8b53-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="a8b53-108">Скрипт также можно выполнить вручную с помощью программы SQL\*Plus.</span><span class="sxs-lookup"><span data-stu-id="a8b53-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="a8b53-109">**Запуск скрипта вручную**</span><span class="sxs-lookup"><span data-stu-id="a8b53-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="a8b53-110">Щелкните **Копировать** , чтобы скопировать скрипт в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="a8b53-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="a8b53-111">Запустите программу SQL\*Plus и перейдите в каталог с базой данных-источником Oracle.</span><span class="sxs-lookup"><span data-stu-id="a8b53-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="a8b53-112">Вставьте скрипт в SQL\*Plus, чтобы выполнить его.</span><span class="sxs-lookup"><span data-stu-id="a8b53-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="a8b53-113">Чтобы сохранить скрипт дополнительного журналирования в текстовый файл, щелкните **Сохранить как** и перейдите в каталог, куда необходимо сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="a8b53-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="a8b53-114">Введите имя файла и нажмите кнопку **Сохранить** , чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="a8b53-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="a8b53-115">Нажмите кнопку **Далее** , чтобы перейти на страницу [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span><span class="sxs-lookup"><span data-stu-id="a8b53-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b53-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8b53-116">See Also</span></span>  
 <span data-ttu-id="a8b53-117">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="a8b53-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="a8b53-118">Обзор и создание скриптов дополнительного журналирования</span><span class="sxs-lookup"><span data-stu-id="a8b53-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
