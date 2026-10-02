# 🚗 Traçar Trajeto com Flutter Maps

Aplicativo desenvolvido em **Flutter/Dart** para demonstrar o uso de mapas, geolocalização por GPS e cálculo de rotas utilizando o **OSRM (Open Source Routing Machine)**.

## 📱 Sobre o projeto

O aplicativo permite obter a localização atual do usuário, selecionar um destino diretamente no mapa e calcular o trajeto entre a origem e o destino.

### Funcionalidades

* 📍 Obtém a localização atual através do GPS.
* 🗺️ Exibe um mapa utilizando o `flutter_map`.
* 👆 Permite selecionar um ponto de destino clicando no mapa.
* 📏 Exibe uma linha entre a origem e o destino.
* 🚗 Utiliza o **OSRM** para calcular um trajeto pelas vias.
* 🛣️ Exibe o trajeto calculado no mapa.
* 📌 Marca a origem e o destino com marcadores.

## 🛠️ Tecnologias utilizadas

* **Flutter**
* **Dart**
* **Flutter Map**
* **OpenStreetMap**
* **Geolocator**
* **OSRM**
* **HTTP**
* **LatLong2**

## 📦 Dependências

As principais dependências utilizadas no projeto são:

```yaml
dependencies:
  flutter:
    sdk: flutter

  flutter_map: ^8.2.2
  latlong2: ^0.9.1
  http: ^1.5.0
  geolocator: ^14.0.2
```

## ⚙️ Instalação

### 1. Clonar o projeto

```bash
git clone URL_DO_REPOSITORIO
```

Entre na pasta do projeto:

```bash
cd trajeto_maps
```

### 2. Instalar as dependências

Execute no terminal:

```bash
flutter pub get
```

### 3. Executar o aplicativo

```bash
flutter run
```

Também é possível executar diretamente pelo VS Code ou Android Studio.

## 🗺️ Como funciona

O funcionamento do aplicativo segue as seguintes etapas:

```text
┌─────────────────────┐
│   Iniciar aplicativo │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Obter localização   │
│      pelo GPS       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Exibir localização  │
│      no mapa        │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Usuário toca em um  │
│ ponto do mapa       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Definir destino     │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Enviar origem e     │
│ destino para OSRM   │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Receber coordenadas │
│       da rota       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Desenhar trajeto    │
│      no mapa        │
└─────────────────────┘
```

## 🌐 OSRM

O **OSRM (Open Source Routing Machine)** é utilizado para calcular o trajeto entre dois pontos.

A requisição utiliza as coordenadas de longitude e latitude da origem e do destino.

Exemplo:

```text
https://router.project-osrm.org/route/v1/driving/
LONGITUDE_ORIGEM,LATITUDE_ORIGEM;
LONGITUDE_DESTINO,LATITUDE_DESTINO
?overview=full&geometries=geojson
```

O aplicativo recebe a resposta em formato JSON e transforma as coordenadas retornadas pelo OSRM em pontos utilizados pelo `Polyline` do mapa.

## 📍 Origem e destino

A origem é obtida através da localização do dispositivo utilizando o pacote `geolocator`.

O destino é definido pelo usuário ao tocar em qualquer ponto do mapa.

A aplicação então utiliza:

```text
Origem = GPS atual
Destino = ponto clicado no mapa
```

## 🔐 Permissões

Para utilizar a localização do dispositivo, é necessário permitir o acesso à localização.

No Android, a permissão deve ser configurada no:

```text
android/app/src/main/AndroidManifest.xml
```

Exemplo:

```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
```

## 📂 Estrutura do projeto

A estrutura principal do projeto está organizada da seguinte forma:

```text
trajeto_maps/
│
├── .dart_tool/
├── .idea/
├── android/
├── assets/
├── build/
├── ios/
│
├── lib/
│   ├── ui/
│   │   └── style/
│   │       ├── colors.dart
│   │       └── theme.dart
│   │
│   ├── widgets/
│   │   └── menu.dart
│   │
│   ├── linha.dart
│   ├── rota.dart
│   ├── splash.dart
│   └── main.dart
│
├── linux/
├── macos/
├── web/
├── windows/
│
├── .flutter-plugins-dependencies
├── .gitignore
├── .metadata
├── analysis_options.yaml
├── pubspec.lock
├── pubspec.yaml
└── README.md
```

## 🎯 Objetivo da atividade

O objetivo da atividade é desenvolver uma aplicação mobile utilizando Flutter e Dart, integrando:

* Geolocalização;
* Mapas;
* Interação com o usuário;
* Requisições HTTP;
* API de rotas;
* Representação gráfica de trajetos.

## 👨‍💻 Desenvolvedor

**Nome:** Heloá Vitória de Oliveira

**Curso:** Téc. Desenvolvimento de Sistemas

**Disciplina:** Desenvolvimento Mobile / Flutter

**Ano:** 2026
