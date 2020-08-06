---
title: Диалоговое окно «сведения об олицетворении» (мастер импорта таблиц) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728926"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a>Диалоговое окно «Сведения об олицетворении» (мастер импорта таблиц)
  Страница **Сведения об олицетворении** служит для указания учетных данных, которые будут использоваться [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для соединения с источником данных. Дополнительные сведения об олицетворении учетных данных см. в разделе [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).  
  
## <a name="options"></a>Варианты  
 **Имя и пароль определенного пользователя Windows**  
 Выберите этот параметр, чтобы в табличной модели использовались учетные данные безопасности указанной пользовательской учетной записи Windows.  
  
 **User name**  
 Введите требуемые домен и имя пользовательской учетной записи. Используйте следующий формат:  
  
 *\<Domain name>* **\\** *\<User account name>*  
  
 Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .  
  
 **Пароль**  
 Введите пароль учетной записи пользователя, которая будет использоваться табличной моделью.  
  
 Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .  
  
 **Учетная запись службы**  
 Выберите этот параметр для использования учетных данных безопасности, связанных со службой [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющей моделью.  
  
## <a name="see-also"></a>См. также:  
 [Олицетворение (табличные службы SSAS)](tabular-models/impersonation-ssas-tabular.md)  
  
  
