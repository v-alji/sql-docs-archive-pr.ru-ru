---
title: Восстановление распределенное воспроизведение установки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666362"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="50a27-102">Восстановление установки распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="50a27-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="50a27-103">При восстановлении компонента распределенного воспроизведения (контроллера или клиента) выполняется следующее.</span><span class="sxs-lookup"><span data-stu-id="50a27-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="50a27-104">Повторная установка всех связанных файлов на диске с заменой существующих файлов.</span><span class="sxs-lookup"><span data-stu-id="50a27-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="50a27-105">Повторное создание учетной записи службы Windows, если соответствующая учетная запись службы была удалена.</span><span class="sxs-lookup"><span data-stu-id="50a27-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="50a27-106">Нельзя использовать операцию восстановления для добавления или удаления компонентов.</span><span class="sxs-lookup"><span data-stu-id="50a27-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="50a27-107">Чтобы добавить или удалить компонент, установите или снимите флажок напротив него в дереве компонентов на странице **Выбор компонентов** в программе установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50a27-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="50a27-108">Восстановление установки распределенного воспроизведения, завершившейся ошибкой</span><span class="sxs-lookup"><span data-stu-id="50a27-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="50a27-109">В меню **Пуск** выберите **Панель управления**, а затем дважды щелкните пункт **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="50a27-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="50a27-110">Выберите [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в окне **Удаление или изменение программы** и нажмите в диалоговом окне [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] кнопку **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="50a27-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="50a27-111">Следуйте инструкциям мастера [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и на странице **Выбор компонентов** выберите компоненты распределенного воспроизведения, которые необходимо восстановить, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="50a27-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="50a27-112">Завершите мастер установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для восстановления выбранных компонентов программы распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="50a27-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
