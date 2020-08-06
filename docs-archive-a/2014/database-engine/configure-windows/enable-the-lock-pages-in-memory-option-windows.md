---
title: Включение параметра "Блокировка страниц в памяти" (Windows) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664492"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="f9af7-102">Включение параметра «Блокировка страниц в памяти» (Windows)</span><span class="sxs-lookup"><span data-stu-id="f9af7-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="f9af7-103">Эта политика Windows определяет, какие учетные записи могут использовать процесс для сохранения данных в физической памяти, чтобы система не отправляла страницы данных в виртуальную память на диске.</span><span class="sxs-lookup"><span data-stu-id="f9af7-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9af7-104">Блокировка страниц в памяти может повысить производительность, если требуется подкачка памяти на диск.</span><span class="sxs-lookup"><span data-stu-id="f9af7-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="f9af7-105">Для включения этой политики для учетной записи, используемой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], воспользуйтесь средством «Групповая политика Windows» (gpedit.msc).</span><span class="sxs-lookup"><span data-stu-id="f9af7-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f9af7-106">Чтобы изменить эту политику, необходимо быть системным администратором.</span><span class="sxs-lookup"><span data-stu-id="f9af7-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="f9af7-107">Включение параметра «Блокировка страниц в памяти»</span><span class="sxs-lookup"><span data-stu-id="f9af7-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="f9af7-108">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f9af7-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="f9af7-109">В поле **Открыть** введите `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="f9af7-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="f9af7-110">В консоли **Редактор локальных групповых политик** разверните узел **Конфигурация компьютера**, затем узел **Конфигурация Windows**.</span><span class="sxs-lookup"><span data-stu-id="f9af7-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="f9af7-111">Разверните узлы **Настройки безопасности**и **Локальные политики**.</span><span class="sxs-lookup"><span data-stu-id="f9af7-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="f9af7-112">Выберите папку **Назначение прав пользователя** .</span><span class="sxs-lookup"><span data-stu-id="f9af7-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="f9af7-113">Политики будут показаны на панели подробностей.</span><span class="sxs-lookup"><span data-stu-id="f9af7-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="f9af7-114">На этой панели дважды щелкните параметр **Блокировка страниц в памяти**.</span><span class="sxs-lookup"><span data-stu-id="f9af7-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="f9af7-115">В диалоговом окне **Параметр локальной безопасности — блокировка страниц в памяти** щелкните **Добавить пользователя или группу**.</span><span class="sxs-lookup"><span data-stu-id="f9af7-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="f9af7-116">В диалоговом окне **Выбор: пользователи, учетные записи служб или группы** добавьте учетную запись, обладающую правами доступа для запуска sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="f9af7-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="f9af7-117">Чтобы изменения вступили в силу, выйдите из системы и снова войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="f9af7-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9af7-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9af7-118">See Also</span></span>  
 [<span data-ttu-id="f9af7-119">Параметры конфигурации сервера «Server Memory»</span><span class="sxs-lookup"><span data-stu-id="f9af7-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
