---
title: Изменение средства разбиения текста на слова, используемого для английского языка (США и Соединенное Королевство) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664838"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="94470-102">Change the Word Breaker Used for US English and UK English</span><span class="sxs-lookup"><span data-stu-id="94470-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="94470-103">устанавливает новую версию (версию 14.0.4999.1038) средства разбиения по словам и парадигматического модуля для английского языка, заменяя предыдущую версию этих компонентов (версию 12.0.6828.0).</span><span class="sxs-lookup"><span data-stu-id="94470-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="94470-104">Дополнительные сведения об изменениях в поведении новых компонентов см. в статье [Изменения в функциях полнотекстового поиска](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="94470-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="94470-105">В этом разделе описывается способ переключения из новой версии этих компонентов в предыдущую версию или обратно из предыдущей версии в новую версию.</span><span class="sxs-lookup"><span data-stu-id="94470-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="94470-106">При работе с кластерными установками эти изменения необходимо вносить на всех основных и пассивных узлах.</span><span class="sxs-lookup"><span data-stu-id="94470-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="94470-107">В предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использовались другие средства разбиения по словам, представленные другими идентификаторами CLSID для английского языка (США) (LCID 1033) и английского языка (Великобритания) (LCID 2057).</span><span class="sxs-lookup"><span data-stu-id="94470-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="94470-108">В этом выпуске оба идентификатора LCID используют одни и те же компоненты с общими идентификаторами CLSID, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="94470-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="94470-109">LCID</span><span class="sxs-lookup"><span data-stu-id="94470-109">LCID</span></span>|<span data-ttu-id="94470-110">Средство разбиения по словам, установленное в предыдущих версиях</span><span class="sxs-lookup"><span data-stu-id="94470-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="94470-111">версия 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="94470-111">version 12.0.6828.0</span></span>|<span data-ttu-id="94470-112">Парадигматический модуль, установленный в предыдущих версиях</span><span class="sxs-lookup"><span data-stu-id="94470-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="94470-113">Средство разбиения по словам, установленное в этой версии</span><span class="sxs-lookup"><span data-stu-id="94470-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="94470-114">версия 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="94470-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="94470-115">Парадигматический модуль, установленный в этой версии</span><span class="sxs-lookup"><span data-stu-id="94470-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="94470-116">1033</span><span class="sxs-lookup"><span data-stu-id="94470-116">1033</span></span><br /><span data-ttu-id="94470-117">(английский, США)</span><span class="sxs-lookup"><span data-stu-id="94470-117">(US English)</span></span>|<span data-ttu-id="94470-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="94470-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="94470-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="94470-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="94470-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="94470-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="94470-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="94470-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="94470-122">2057</span><span class="sxs-lookup"><span data-stu-id="94470-122">2057</span></span><br /><span data-ttu-id="94470-123">(английский, Великобритания)</span><span class="sxs-lookup"><span data-stu-id="94470-123">(UK English)</span></span>|<span data-ttu-id="94470-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="94470-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="94470-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="94470-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="94470-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="94470-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="94470-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="94470-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="94470-128">Компоненты, описанные в этой статье, представляют собой DLL-файлы, которые устанавливаются в папку `MSSQL\Binn` для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94470-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="94470-129">Полный путь обычно выглядит следующим образом: `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="94470-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="94470-130">Дополнительные сведения о средствах разбиения по словам и парадигматических модулях см. в статье [Настройка и управление средством разбиения на слова и парадигматические модули для поиска](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="94470-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="94470-131">Переключение из текущего средства разбиения по словам для английского языка в предыдущие средства разбиения по словам для английского языка</span><span class="sxs-lookup"><span data-stu-id="94470-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="94470-132">Переход от текущей версии средства разбиения по словам для английского языка (США) к предыдущей версии</span><span class="sxs-lookup"><span data-stu-id="94470-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="94470-133">Перейдите к следующему разделу реестра: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="94470-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="94470-134">Чтобы добавить новые разделы для идентификаторов классов COM предыдущей версии интерфейсов средства разбиения по словам для английского языка (США) и парадигматического модуля для идентификатора LCID 1033, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="94470-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="94470-135">Добавите новый раздел со значением **{188D6CC5-CB03-4 C 01-912E-47D21295D77E}** для предыдущего средства разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="94470-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="94470-136">Обновите данные (по умолчанию) значения этого раздела до **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="94470-137">Добавьте новый раздел со значением **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** для предыдущей версии парадигматического модуля.</span><span class="sxs-lookup"><span data-stu-id="94470-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="94470-138">Обновите данные (по умолчанию) значения этого раздела до **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="94470-139">Перейдите к следующему узлу: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<корень_экземпляра\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="94470-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="94470-140">Обновите значение раздела **WBreakerClass** до **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="94470-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="94470-141">Обновите значение раздела **StemmerClass** до **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="94470-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="94470-142">Перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94470-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="94470-143">Переход от текущей версии средства разбиения по словам для английского языка (Соединенное Королевство) к предыдущей версии</span><span class="sxs-lookup"><span data-stu-id="94470-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="94470-144">Перейдите к следующему разделу реестра: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="94470-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="94470-145">Чтобы добавить новый раздел для идентификаторов классов COM для предыдущей версии интерфейсов средства разбиения по словам для английского языка (Соединенное Королевство) и парадигматического модуля для идентификатора LCID 2057, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="94470-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="94470-146">Добавьте новый раздел со значением **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** для предыдущего средства разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="94470-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="94470-147">Обновите данные (по умолчанию) значения этого раздела до **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="94470-148">Добавьте новый раздел со значением **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** для предыдущей версии парадигматического модуля.</span><span class="sxs-lookup"><span data-stu-id="94470-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="94470-149">Обновите данные (по умолчанию) значения этого раздела до **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="94470-150">Перейдите к следующему узлу: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<корень_экземпляра\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="94470-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="94470-151">Обновите значение раздела **WBreakerClass** до **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="94470-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="94470-152">Обновите значение раздела **StemmerClass** до **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="94470-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="94470-153">Перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94470-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="94470-154">Переключение обратно из предыдущего средства разбиения по словам для английского языка в текущее средство разбиения по словам для английского языка</span><span class="sxs-lookup"><span data-stu-id="94470-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="94470-155">Переход обратно от предыдущей версии средства разбиения по словам для английского языка (США) к текущей версии</span><span class="sxs-lookup"><span data-stu-id="94470-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="94470-156">Перейдите к следующему разделу реестра: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="94470-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="94470-157">Если следующие разделы реестра не существуют, выполните следующие действия, чтобы добавить новый раздел для идентификаторов классов COM для текущей версии интерфейсов средства разбиения по словам для английского языка (США) и парадигматического модуля для идентификатора LCID 1033.</span><span class="sxs-lookup"><span data-stu-id="94470-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="94470-158">Добавьте новый раздел со значением **{9faed859-0b30-4434-ae65-412e14a16fb8}** для текущего средства разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="94470-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="94470-159">Обновите данные (по умолчанию) значения этого раздела до **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="94470-160">Добавьте новый раздел со значением **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** для текущего парадигматического модуля.</span><span class="sxs-lookup"><span data-stu-id="94470-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="94470-161">Обновите данные (по умолчанию) значения этого раздела до **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="94470-162">Перейдите к следующему узлу: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<корень_экземпляра\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="94470-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="94470-163">Обновите значение раздела **WBreakerClass** до **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="94470-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="94470-164">Обновите значение раздела **StemmerClass** до **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="94470-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="94470-165">Перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94470-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="94470-166">Переход обратно от предыдущей версии средства разбиения по словам для английского языка (Соединенное Королевство) к текущей версии</span><span class="sxs-lookup"><span data-stu-id="94470-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="94470-167">Перейдите к следующему разделу реестра: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="94470-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="94470-168">Если следующие разделы реестра не существуют, выполните следующие действия, чтобы добавить новый раздел для идентификаторов классов COM для текущей версии интерфейсов средства разбиения по словам для английского языка (Соединенное Королевство) и парадигматического модуля для идентификатора LCID 2057.</span><span class="sxs-lookup"><span data-stu-id="94470-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="94470-169">Добавьте новый раздел со значением **{9faed859-0b30-4434-ae65-412e14a16fb8}** для текущего средства разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="94470-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="94470-170">Обновите данные (по умолчанию) значения этого раздела до **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="94470-171">Добавьте новый раздел со значением **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** для текущего парадигматического модуля.</span><span class="sxs-lookup"><span data-stu-id="94470-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="94470-172">Обновите данные (по умолчанию) значения этого раздела до **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="94470-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="94470-173">Перейдите к следующему узлу: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<корень_экземпляра\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="94470-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="94470-174">Обновите значение раздела **WBreakerClass** до **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="94470-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="94470-175">Обновите значение раздела **StemmerClass** до **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="94470-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="94470-176">Перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94470-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94470-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="94470-177">See Also</span></span>  
 <span data-ttu-id="94470-178">[Перевод средств разбиения по словам, используемых поиском, на предыдущую версию](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="94470-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="94470-179">Изменения в функциях полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="94470-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
