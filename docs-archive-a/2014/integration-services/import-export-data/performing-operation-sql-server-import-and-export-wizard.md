---
title: Выполнение операции (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666153"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="df211-102">Выполнение операции (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="df211-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="df211-103">Используйте страницу **выполнение операции** для просмотра хода выполнения и результатов операции импорта и экспорта, а также для прерывания операции при необходимости.</span><span class="sxs-lookup"><span data-stu-id="df211-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="df211-104">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df211-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="df211-105">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df211-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="df211-106">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="df211-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="df211-107">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="df211-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="df211-108">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="df211-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="df211-109">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df211-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="df211-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="df211-110">Options</span></span>  
 <span data-ttu-id="df211-111">**Действие**</span><span class="sxs-lookup"><span data-stu-id="df211-111">**Action**</span></span>  
 <span data-ttu-id="df211-112">Отображает каждое действие, являющееся частью операции.</span><span class="sxs-lookup"><span data-stu-id="df211-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="df211-113">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="df211-113">**Status**</span></span>  
 <span data-ttu-id="df211-114">Отображает успешное или сбойное выполнение каждого действия.</span><span class="sxs-lookup"><span data-stu-id="df211-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="df211-115">**Message**</span><span class="sxs-lookup"><span data-stu-id="df211-115">**Message**</span></span>  
 <span data-ttu-id="df211-116">Отображает уведомления и сообщения об ошибках, которые могут появляться в ходе действия.</span><span class="sxs-lookup"><span data-stu-id="df211-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="df211-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="df211-117">**Filter**</span></span>  
 <span data-ttu-id="df211-118">Позволяет выбрать отображение только ошибок, предупреждений или сообщений об успешно выполненных действиях.</span><span class="sxs-lookup"><span data-stu-id="df211-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="df211-119">Можно вернуться к отображению по умолчанию, выбрав **Показать все действия**.</span><span class="sxs-lookup"><span data-stu-id="df211-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="df211-120">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="df211-120">**Stop**</span></span>  
 <span data-ttu-id="df211-121">При необходимости прерывать операцию, используя кнопку **остановить** .</span><span class="sxs-lookup"><span data-stu-id="df211-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="df211-122">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="df211-122">**Report**</span></span>  
 <span data-ttu-id="df211-123">Позволяет просмотреть отчет о результатах, сохранить его в файл, скопировать его в буфер обмена или отправить по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="df211-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
