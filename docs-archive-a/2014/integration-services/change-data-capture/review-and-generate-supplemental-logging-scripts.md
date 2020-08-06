---
title: Обзор и создание скриптов дополнительного журналирования | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657850"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="d115c-102">Обзор и создание скриптов дополнительного журналирования</span><span class="sxs-lookup"><span data-stu-id="d115c-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="d115c-103">Вкладка **Скрипты** служит для запуска или повторного запуска скрипта в базе данных-источнике Oracle, для которой задано дополнительное журналирование.</span><span class="sxs-lookup"><span data-stu-id="d115c-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="d115c-104">Перед запуском скрипта выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="d115c-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="d115c-105">**Включить изменения в этой сеанс**</span><span class="sxs-lookup"><span data-stu-id="d115c-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="d115c-106">Выберите этот параметр, чтобы запустить скрипт для всех новых таблиц, добавленных в экземпляр CDC, или таблиц, в которые были внесены какие-либо изменения с помощью редактора свойств.</span><span class="sxs-lookup"><span data-stu-id="d115c-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d115c-107">Если в таблицы из экземпляра CDC не было внесено никаких изменений, то область скрипта дополнительного журналирования Oracle будет пустой.</span><span class="sxs-lookup"><span data-stu-id="d115c-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="d115c-108">**Включить все таблицы/экземпляры отслеживания**</span><span class="sxs-lookup"><span data-stu-id="d115c-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="d115c-109">Выберите этот параметр, чтобы выполнить скрипт во всех таблицы и экземплярах отслеживания из экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="d115c-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="d115c-110">Выбрав один из этих параметров, запустите скрипт дополнительного журналирования.</span><span class="sxs-lookup"><span data-stu-id="d115c-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="d115c-111">Запуск скриптов дополнительного журналирования</span><span class="sxs-lookup"><span data-stu-id="d115c-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="d115c-112">Нажмите кнопку **Выполнить скрипт** , чтобы запустить скрипт дополнительного журналирования в таблицах, определенных для экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="d115c-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="d115c-113">Этот скрипт настраивает базу данных Oracle таким образом, что все интересующие столбцы будут записываться в журналы транзакций базы данных при регистрации операций UPDATE для отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="d115c-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="d115c-114">Как правило, этот скрипт проверяет и выполняет системный администратор Oracle.</span><span class="sxs-lookup"><span data-stu-id="d115c-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="d115c-115">При выполнении скриптов дополнительного журналирования открывается диалоговое окно «Учетные данные Oracle для выполнения скриптов», в которое необходимо ввести допустимые имя пользователя Oracle и пароль.</span><span class="sxs-lookup"><span data-stu-id="d115c-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="d115c-116">Сведения об указании надлежащих учетных данных Oracle см. в разделе [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="d115c-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="d115c-117">При необходимости скрипты также можно запускать вручную с помощью SQL\*Plus.</span><span class="sxs-lookup"><span data-stu-id="d115c-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="d115c-118">Запуск скрипта вручную</span><span class="sxs-lookup"><span data-stu-id="d115c-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="d115c-119">Щелкните **Копировать** , чтобы скопировать скрипт в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d115c-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="d115c-120">Запустите программу SQL\*Plus и перейдите в каталог с базой данных-источником Oracle.</span><span class="sxs-lookup"><span data-stu-id="d115c-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="d115c-121">Вставьте скрипт в SQL\*Plus, чтобы выполнить его.</span><span class="sxs-lookup"><span data-stu-id="d115c-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="d115c-122">Сохранение скрипта дополнительного журналирования в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="d115c-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="d115c-123">Щелкните **Сохранить как** и перейдите в каталог, куда необходимо сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="d115c-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="d115c-124">Введите имя файла и нажмите кнопку **Сохранить** , чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="d115c-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d115c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d115c-125">See Also</span></span>  
 <span data-ttu-id="d115c-126">[Как изменить свойства экземпляра CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d115c-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="d115c-127">Учетные данные Oracle для выполнения скрипта</span><span class="sxs-lookup"><span data-stu-id="d115c-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
