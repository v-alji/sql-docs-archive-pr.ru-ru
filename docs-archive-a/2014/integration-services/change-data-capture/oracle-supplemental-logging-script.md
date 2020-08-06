---
title: Скрипт дополнительного журналирования Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728581"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="5d77c-102">Скрипт дополнительного журналирования Oracle</span><span class="sxs-lookup"><span data-stu-id="5d77c-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="5d77c-103">В этом диалоговом окне отображается скрипт дополнительного журналирования Oracle.</span><span class="sxs-lookup"><span data-stu-id="5d77c-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="5d77c-104">При подготовке экземпляра CDC к использованию конструктор CDC создает скрипт для Oracle SQL, который настраивает дополнительное журналирование для отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="5d77c-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="5d77c-105">Скрипт дополнительного журналирования настраивает Oracle таким образом, чтобы при обновлении определенной таблицы записи об изменениях, которые заносятся в журнал транзакций, содержали данные всех интересующих столбцов, а не только измененных.</span><span class="sxs-lookup"><span data-stu-id="5d77c-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="5d77c-106">В зависимости от действующих в организации политик Oracle DBA для выполнения скрипта дополнительного журналирования может потребоваться утверждение администратора базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="5d77c-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d77c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d77c-107">Options</span></span>  
 <span data-ttu-id="5d77c-108">Ниже приведены поддерживаемые параметры выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="5d77c-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="5d77c-109">**Запустить сценарий**</span><span class="sxs-lookup"><span data-stu-id="5d77c-109">**Run Script**</span></span>  
 <span data-ttu-id="5d77c-110">Выполняет скрипт дополнительного журналирования в таблицах, определенных для экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="5d77c-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="5d77c-111">Чтобы запустить этот скрипт, пользователь Oracle должен иметь разрешение ALTER TABLE для всех таблиц, которые будут отслеживаться, а также разрешение SELECT на представление DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="5d77c-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="5d77c-112">Кроме того, пользователь Oracle должен иметь учетные данные в базе данных Oracle со всеми необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="5d77c-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="5d77c-113">Можно определить запрос учетных данных Oracle с последующим выполнением скрипта.</span><span class="sxs-lookup"><span data-stu-id="5d77c-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="5d77c-114">**Сохранить как**</span><span class="sxs-lookup"><span data-stu-id="5d77c-114">**Save As**</span></span>  
 <span data-ttu-id="5d77c-115">Сохраняет скрипт в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="5d77c-115">Saves the script to a text file.</span></span> <span data-ttu-id="5d77c-116">Этот параметр используется в том случае, когда администратору базы данных Oracle необходимо ознакомиться со скриптом дополнительного журналирования перед его выполнением. Программа позволяет сохранить скрипт в текстовый файл, который можно будет отправить администратору базы данных Oracle по электронной почте или другому каналу для последующего выполнения (с помощью служебной программы Oracle SQL\*Plus или другого средства для выполнения скриптов в базе данных Oracle).</span><span class="sxs-lookup"><span data-stu-id="5d77c-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="5d77c-117">**Copy**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-117">**Copy**</span></span>  
 <span data-ttu-id="5d77c-118">Копирует скрипт в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5d77c-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="5d77c-119">Когда все будет готово, скрипт дополнительного журналирования можно вставить в нужное место, если администратору базы данных Oracle необходимо ознакомиться с ним перед выполнением.</span><span class="sxs-lookup"><span data-stu-id="5d77c-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d77c-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d77c-120">See Also</span></span>  
 <span data-ttu-id="5d77c-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="5d77c-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="5d77c-122">Управление экземпляром CDC</span><span class="sxs-lookup"><span data-stu-id="5d77c-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
