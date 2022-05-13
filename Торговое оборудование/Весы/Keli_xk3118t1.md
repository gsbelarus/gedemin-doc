Порядок настройки монорельсовых весов Keli xk3118t1
 1. Нажать и удерживать клавишу "РЕЖ" до звукового сигнала;
 2. Нажать два раза клавишу "НОЛЬ";
    На экране будет "br4800" - скорость СОМ-порта;
    Если не 4800 нажимаем клавишу "СУММА" несколько раз до 4800;
    Нажимаем клавишу "НОЛЬ";
 3. На экране: "Со 5" - режим передачи данных;
    Если не 5, клавишей "СУММА" выставляем 5;
    Нажимаем клавишу "НОЛЬ";
 4. Нажимаем однократно клавишу "РЕЖ" - для выхода с режима настроек.

Отправка запроса веса:
`Sender.OwnerForm.GetComponent("usrg_gsComScaner1").PutString(Chr(2) & Chr(66) & Chr(3))`

Обработка получения:

```BarCode = Sender.Barcode
      If Left(BarCode, 2) = "NW" Then
        i = Len(BarCode)
        WeightStr = Mid(BarCode, 4, i - 7)
        WeightStr = Replace(WeightStr, ".", Application.DecimalSeparatorSys)
        Weight = CSng(WeightStr)
      End If 
```

