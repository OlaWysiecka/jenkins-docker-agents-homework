# Automatycznie skalowani agenci Docker w Jenkins



Celem zadania jest skonfigurowanie Docker jako źródła automatycznie uruchamianych agentów Jenkins.

Pipeline jest wykonywany na agencie uruchamianym jako kontener Docker.

## Konfiguracja

Skonfigurowano:
* Docker Desktop jako środowisko uruchomieniowe kontenerów 
* Jenkins z dostępem do Docker Engine 
* Docker Cloud w Jenkins
* Docker Agent Template
* agenta o etykiecie docker-agent
* obraz agenta jenkins/agent:latest-jdk17

## Pipeline

Pipeline wykonuje się na agencie Docker i sprawdza:
* system operacyjny za pomocą cat /etc/os-release
* wersję kernela za pomocą uname -a
* użytkownika za pomocą whoami
* dostępność Javy za pomocą java -version


## Oczekiwany rezultat

Po uruchomieniu pipeline'u Jenkins automatycznie uruchamia kontener Docker jako agenta, wykonuje na nim kolejne etapy, a następnie kończy pracę agenta.


W logach pipeline'u powinny być widoczne informacje dotyczące systemu działającego wewnątrz kontenera Docker.