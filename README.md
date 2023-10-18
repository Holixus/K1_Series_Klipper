Welcome to the Creality K1 series Klipper project!

This is clone from https://github.com/Klipper3d/klipper/

[![Klipper](docs/img/klipper-logo-small.png)](https://www.klipper3d.org/)

https://www.klipper3d.org/

Used on Creality K1 series devices

We are https://github.com/Klipper3d/klipper/ Updated relevant functions on the basis

release： https://github.com/CrealityOfficial/K1_Series_Klipper/releases/tag/V1.3.2.1

firmware-recovery-tool: https://github.com/CrealityOfficial/K1_Series_Annex/releases/tag/V1.0.0

# Что изменили Creality в Klipper для принтеров серии K1

* Заменены все диагностические сообщения на сообщения в формате JSON с кодами, форматами и параметрами;
* Добавлена поддержка сохранения в EEPROM (и куча команд для этого);
* У команды M140 добавленно жесткое ограничение максимальной температуры 110 градусов;
* Переработан алгоритм нагрева BangBang;
* Да и с PID тоже что-то подтюнили;
* Что-то изменили в ожидании температуры;
* Немного вмешались в парковку головки, чтобы без парговки по X и Y нельзя было парковать Z;
* klippy/extras/metadata.py -- чтение параметров печати из g-code (поддерживаются только PrusaSlicer, Slic3rPE, Slic3r, Cura, Simplify3D, KISSlicer, IdeaMaker, IceSL, KiriMoto, Creality);
* Пауза/продолжение с сохранением в EEPROM (энергонезависимую память);
* Внедренна поддержка проприетаного prtouch_v2 (с помощью 4х тензорных датчиков под столом);
* klippy/extras/shaper_calibrate.py:;
  * Вычисление шейперов выполняется внешней программой на C++ для меньшего потребления памяти с передачей данный через разделяемую память;
  * Добавлен список допустимых шейперов (в оригинале его нет);
* Добавлена поддедка микроконтроллеров GigaDevices gd32f303xe;
* Отключение нагревателей в случае ошибки нагрева;
* Какие-то доработки в парковке без концевых датчикой. Полагаю, регламентирующие порядок парковки осей;
* Добавлены команды
  * CSSAVE_CONFIG -- как SAVE_CONFIG только с без запроса на перезапуск системы
  * BED_MESH_SAVE -- Временно сохранить mesh во внутреннюю переменную
  * BED_MESH_RESTORE -- Восстановить mesh из внутренней переменной
  * BED_MESH_SET_DISABLE -- отключить коррекцию mesh
  * BED_MESH_SET_ENABLE -- включить коррекцию mesh
  * EEPROM_DEBUG_READ
  * EEPROM_DEBUG_WRITE_BYTE
  * EEPROM_DEBUG_WRITE_INT
  * EEPROM_DEBUG_WRITE_FLOAT
  * EEPROM_READ
  * EEPROM_WRITE_BYTE
  * EEPROM_WRITE_INT
  * EEPROM_WRITE_FLOAT
  * EEPROM_IS_FIRST_USED
  * EEPROM_POS
  * EEPROM_PRINTER_INFO
  * CX_PRINT_LEVELING_CALIBRATION -- Калибровка уровней стола
  * CX_CLEAN_CALIBRATION_FLAGS -- Сбросить флаги калибрации
  * CX_PRINT_DRAW_ONE_LINE -- Нарисовать линию для прочистки сопла перед печатью
  * CX_ROUGH_G28 -- Быстрая парковка головки (homing)
  * CX_NOZZLE_CLEAR -- очистка сопла от пластика
  * QUERY_FAN_CHECK -- Check CXSW Special Fan Status
  * CX_RESTORE_GCODE_STATE -- Restore a previously saved G-Code state
  * SAVE_GCODE_STATE -- Save G-Code coordinate state
  * GET_POSITION
  * SET_POSITION -- SET_POSITION information on the current location of the toolhead
  * STEPPER_Z_SENEORLESS -- это у них опечатка
  
