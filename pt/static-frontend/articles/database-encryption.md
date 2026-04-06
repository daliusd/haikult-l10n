---
title: 'Os seus dados estão encriptados: Porque é que isso é importante'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Todas as bases de dados de utilizadores do Haiku.lt são encriptadas em repouso. Aqui está o que isso realmente significa e porque deve preocupar-se.

## O que significa a encriptação (simplesmente)

Imagine as suas faturas e dados de clientes como um diário. A encriptação bloqueia esse diário e transforma cada palavra numa algaraviada aleatória. Sem a chave, alguém que tenha o diário na mão não vê nada para além de ruído — `X7k#mQ2$pL9@vR4...` — completamente ilegível.

A base de dados de cada utilizador recebe uma chave única, e o Haiku.lt nunca armazena essa chave em texto simples.

## O cenário de backup

O Haiku.lt faz backups regulares para se proteger contra a perda de dados. Agora imagine o pior cenário possível: um hacker de alguma forma apodera-se de um desses ficheiros de backup.

O que é que eles têm? Um ficheiro cheio de palavras baralhadas. Sem a chave de encriptação, a cópia de segurança não tem qualquer valor para eles. Não podem ler os nomes dos seus clientes, os montantes das faturas ou quaisquer outros dados.

## Quão forte é «encriptado»?

O Haiku.lt utiliza encriptação AES-256 — o mesmo padrão utilizado por bancos e governos em todo o mundo. Para fazer força bruta numa chave AES-256, um atacante teria de tentar 2²⁵⁶ combinações possíveis.

Para termos uma perspetiva: mesmo usando todos os computadores da Terra a funcionar a toda a velocidade, decifrar uma única chave AES-256 demoraria mais tempo do que a idade atual do universo. Não é um ataque prático.

## O resultado final

Se as cópias de segurança do Haiku.lt fossem alguma vez roubadas, os seus dados permaneceriam protegidos. A encriptação assegura que a posse física de um ficheiro de cópia de segurança não tem qualquer significado sem a chave de encriptação.

As suas faturas são o seu negócio. Devem continuar a ser suas.
