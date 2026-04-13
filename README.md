# Infraestrutura-Hibrida-DHCP-AWS
   Estudo de Caso: Infraestrutura Híbrida (Local to Cloud) com DHCP, Web Services e AWS
   Descrição do Projeto

Este projeto documenta o planeamento e a implementação de uma infraestrutura de rede completa, evoluindo de uma simulação lógica para um ambiente virtualizado local e, finalmente, para a implementação em nuvem pública (AWS). O objetivo foi garantir a alta disponibilidade de serviços web e a gestão automatizada de endereçamentos IP através de protocolos padrão de mercado.
   Arquitetura e Etapas de Implementação
1. Modelação Lógica (Cisco Packet Tracer)

    Estruturação inicial da topologia de rede utilizando 1 Switch (2960-24TT), 1 Servidor e 2 Desktops.

    Configuração de serviços de DHCP, DNS e HTTP em ambiente simulado para validação de conectividade.

 <img width="459" height="554" alt="Figura 2 da Página 1 - Conexão das máquinas no Packet Tracer" src="https://github.com/user-attachments/assets/35e3246a-d763-497f-ba43-4105746a17d7" />


2. Infraestrutura Local (VirtualBox & Ubuntu Server)

    Implementação de máquinas virtuais com Ubuntu Server e Desktop, ajustando a placa de rede para o modo adequado de isolamento de tráfego.

    Configuração do serviço isc-dhcp-server com escopos de IP (192.168.100.x) e tempos de lease personalizados.

<img width="969" height="559" alt="USEAQUIImagemdaPagina8ou9-Configuracoes de Rede no VirtualBox" src="https://github.com/user-attachments/assets/7d246807-540c-4574-aced-708bfbebf099" />

    Subida de um Servidor Web Apache2 para disponibilização de conteúdo institucional e configuração de permissões de diretório.

 <img width="1695" height="487" alt="USE AQUI Imagem da Página 17 - Site Ola Romualdo! acessado via IP local 192 168 100 51" src="https://github.com/user-attachments/assets/34a57620-3550-4c53-824b-121fc7463346" />



    Análise de Tráfego (Wireshark): Inspeção e validação do protocolo BOOTP/DHCP, identificando as etapas de Request e ACK durante o provisionamento de IPs.

  <img width="754" height="730" alt="Tabela da Página 20 - Captura de pacotes DHCP no Wireshark" src="https://github.com/user-attachments/assets/5451bc1a-ec36-4ffe-a007-08a5d8644012" />


3. Migração para a Nuvem (AWS EC2 & NGINX)

    Provisionamento de uma instância EC2 (Ubuntu 24.04 LTS) na região Canada Central via AWS Academy.

    Gestão de acessos via chaves RSA (.pem) e configuração de Security Groups para liberação de tráfego SSH, HTTP e HTTPS.

    <img width="1175" height="681" alt="Imagem da Pagina 24 - Configuracoes de FirewallSecurity Groups na AWS" src="https://github.com/user-attachments/assets/9aefbeee-b07c-4e9d-8936-0216110b383b" />


    Implementação do NGINX como servidor web de alto desempenho na nuvem, garantindo a escalabilidade da aplicação.

    <img width="327" height="776" alt="Site rodando na nuvem acessado pelo IP Publico da AWS" src="https://github.com/user-attachments/assets/7f2dc3da-6ea7-4861-aaa8-e5bcc094527c" />


   Stack Tecnológica

    Simulação: Cisco Packet Tracer.

    Virtualização: Oracle VirtualBox.

    Sistemas Operacionais: Ubuntu Server & Desktop.

    Servidores Web: Apache2 (Local) e NGINX (Cloud).

    Segurança: SSH, UFW Firewall e AWS Security Groups.

    Análise: Wireshark.

   Aprendizados e Resultados

    Gestão de Infraestrutura como Serviço (IaaS): Ciclo completo de vida de uma instância na AWS, desde a criação do par de chaves até a exposição pública do serviço.

    Troubleshooting de Redes: Capacidade de diagnosticar falhas de comunicação através da análise de pacotes e logs do sistema.

    Cultura DevOps: Introdução a conceitos de automação de redes, segurança de perímetros e migração para ambientes de nuvem.

Projeto desenvolvido por: Paulo Ricardo Ferreira Lacerda.
