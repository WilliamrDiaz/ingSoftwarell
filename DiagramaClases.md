# Diagrama de clases adapater
```plantuml
@startuml
interface DeviceUSB {
    +connect(): void
}

class DeviceOld {
    +connect(): void
}

interface DeviceUSB_C {
    +connectByUSB_C(): void
}

class AdapterUSB {
    - device: DeviceOld
    +connectByUSB_C(): void
}

DeviceUSB <|.. DeviceOld
DeviceUSB_C <|.. AdapterUSB

AdapterUSB --> DeviceOld : uses

@enduml
```
# Diagrama de clases Facade
```plantuml
class MusicPlayer {
    - playerMP3: MP3Player
    - volumeControl: VolumeControl
    - equalizer: Equalizer
    + MusicPlayer()
    + play(file: String): void
    + stop(): void
    + adjustVolume(level: int): void
    + adjustEqualizer(bajo: int, medio: int, alto: int): void
}

class MP3Player {
    + playFile(file: String): void
    + stopPlayback(): void
}

class VolumeControl {
    - nivel: int
    + setNivel(nivel: int): void
}

class Equalizer {
    - bajo: int
    - medio: int
    - alto: int
    + setBajo(bajo: int): void
    + setMedio(medio: int): void
    + setAlto(alto: int): void
}

MusicPlayer *-- MP3Player
MusicPlayer *-- VolumeControl
MusicPlayer *-- Equalizer
```

![Nombre de la imagen](LogoRAM.png)
![Diagrama de clases](http://www.plantuml.com/plantuml/png/XLBBJiCm4BpdA_Re0Zbnywc0u1PK2Ocxcop8PHCNFof1nR_ZFB9Ev4hD8R9trZCxezqwhwmFBHKrAUUW2axNEr8_QE5SGFnAE0xNQdSl8Vv6S89EXaABJwRprf24z-LrQi7le4Z_efNmF1y7w7Of9ZPJhHSJ7vfGmfktkllSoAYYcmbstXp5kgIQGt1-b1Q49oG9klENcdW0iLS7CxJTGOkDdi-Al5cz_Yl6O99pE2ycVOc3NfcsVxLNzPV8A5TfSTgTdXtC9EXV-vfW99-EZJ4D6nplx98BR3N9FCOtd0oBC5pr528HPGqFaL9SYd2vLJTbcSBCa5Kc6PeMQ8jT4xVs7m00)
