---
title: Метод GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658632"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a>Метод GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting)
  Формирует скрипт SQL, который можно использовать для создания базы данных сервера отчетов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a>Параметры  
 *Databasename*  
 Строка, которая содержит имя создаваемой базы данных сервера отчетов.  
  
 *Код языка*  
 Значение, используемое для локализованных имен ролей.  
  
 *IsSharePointMode*  
 Указывает, следует ли создать базу данных в собственном режиме или в режиме SharePoint.  
  
> [!IMPORTANT]  
>  Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , *исшарепоинтмоде* = `True` не поддерживается, так как в режиме интеграции с SharePoint [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] является общей службой SharePoint и не контролируется поставщиком WMI. Этот параметр должен всегда быть установлен в значение `False`.  
  
 *Скрипт*  
 [out] Строка, содержащая сформированный скрипт SQL.  
  
 *HRESULT*  
 [out] Значение, которое указывает, окончился ли вызов успехом или сбоем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода. Значение 0 указывает, что вызов метода завершился успешно. Ненулевое значение указывает, что произошла ошибка.  
  
## <a name="remarks"></a>Remarks  
 Этот метод формирует скрипт SQL, создающий базы данных сервера отчетов для версии сервера отчетов, подключенного в настоящее время.  
  
 Значение, переданное в параметре *DatabaseName* , должно соответствовать контексту именования в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 При создании скрипта этот метод не проверяет существование базы данных.  
  
 Этот метод не проверяет при создании скрипта наличие базы данных сервера отчетов.  
  
 Созданный скрипт поддерживает [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Элементы MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
