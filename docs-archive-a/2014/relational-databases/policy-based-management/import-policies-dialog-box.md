---
title: Диалоговое окно "Импорт политик" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655695"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="df642-102">Диалоговое окно «Импорт политик»</span><span class="sxs-lookup"><span data-stu-id="df642-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="df642-103">Это диалоговое окно используется для импорта одной или нескольких политик (и упоминаемого в них условия), сохраненных в виде XML-файлов, в текущий экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df642-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="df642-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="df642-104">Options</span></span>  
 <span data-ttu-id="df642-105">**Файлы, подлежащие импорту**</span><span class="sxs-lookup"><span data-stu-id="df642-105">**Files to import**</span></span>  
 <span data-ttu-id="df642-106">Чтобы выполнить импорт политики из XML-файла, введите путь и имя файла или нажмите кнопку "Обзор" ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="df642-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="df642-107">**Заменять дубликаты импортируемыми элементами**</span><span class="sxs-lookup"><span data-stu-id="df642-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="df642-108">Выберите, чтобы перезаписать любую существующую политику или условие с тем же именем, если они уже существуют в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df642-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="df642-109">Перезаписать условие с зависимой политикой можно только в том случае, если зависимая политика также переписывается.</span><span class="sxs-lookup"><span data-stu-id="df642-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="df642-110">Если данный параметр не выбран, то наличие условия с таким же выражением не вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="df642-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="df642-111">**Состояние политики**</span><span class="sxs-lookup"><span data-stu-id="df642-111">**Policy state**</span></span>  
 <span data-ttu-id="df642-112">Выберите требуемое состояние для импортированной политики:</span><span class="sxs-lookup"><span data-stu-id="df642-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="df642-113">**Сохранить состояние политики при импорте**</span><span class="sxs-lookup"><span data-stu-id="df642-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="df642-114">**Включить все политики при импорте**</span><span class="sxs-lookup"><span data-stu-id="df642-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="df642-115">**Выключить все политики при импорте**</span><span class="sxs-lookup"><span data-stu-id="df642-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df642-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="df642-116">See Also</span></span>  
 <span data-ttu-id="df642-117">[Администрирование серверов с помощью управления на основе политик](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="df642-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="df642-118">[Импорт политики управления на основе политик](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="df642-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="df642-119">Экспорт политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="df642-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
