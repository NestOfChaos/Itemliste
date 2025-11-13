---
title: Info
layout: page
permalink: /info
store: false
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Willkommen

Willkommen im Stream von [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }}).
Dieser Stream nutzt die Mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787), um ein interaktives Erlebnis zu ermöglichen.
Die Mod hat viele Funktionen, die selbst für erfahrene Nutzer zunächst etwas kompliziert wirken können – aber diese kurze Anleitung hilft dir, dich schnell zurechtzufinden.
Leider kann aus technischen Gründen nicht alles auf Deutsch übersetzt werden - ich hoffe das ist okay.

## Was ist das Twitch Toolkit?

Twitch Toolkit ist eine Mod von **hodlhodl**, die es Zuschauern erlaubt, das Spiel auf verschiedene Arten zu beeinflussen.
Das auffälligste Merkmal ist der [Shop]({{- "/" | relative_url -}}), in dem du eine Auswahl an vom Streamer kuratierten Dingen kaufen kannst.
Je nach Kauf erscheinen diese Gegenstände im Spiel oder wirken sich auf das Spielgeschehen aus.
Eine weitere Möglichkeit zur Interaktion bieten die **Abstimmungen** (Polls) der Mod.

## Was sind Coins?

Coins sind die Währung der Mod.
Du kannst dein Guthaben mit dem Befehl `{{ bal }}` anzeigen lassen.

{% if utils == true %}
Dir wird vielleicht auffallen, dass der Balance-Befehl einige Emojis enthält.
Hier ist eine Übersicht der Bedeutungen:

* 💰 steht für die Anzahl der Coins, die du aktuell besitzt.
* ⚖ steht für dein aktuelles Karma.
* 📈 zeigt an, wie viele Coins du jedes Mal erhältst, wenn die Mod Coins vergibt.
* 📉 zeigt an, wie viele Coins du jedes Mal verlierst, wenn die Mod Coins vergibt.

{% endif %}

{%- if lootboxes == true -%}
Du wirst außerdem eine Nachricht vom Bot über eine **Lootbox** erhalten.
Du kannst diese Lootbox mit dem Befehl `!openlootbox` öffnen und mit `!lootboxes` prüfen, wie viele du besitzt.
Du bekommst jeden Tag eine neue Lootbox.
{%- endif -%}

<br/>

## Was ist Karma?

Karma ist ein System innerhalb der Mod, das begrenzen soll, wie viele **negative Ereignisse** ein Zuschauer gleichzeitig kaufen kann.
Das System funktioniert, indem es direkt beeinflusst, wie viele Coins ein Zuschauer jedes Mal erhält, wenn die Mod Coins vergibt.
Das bedeutet: Je niedriger dein Karma ist, desto weniger Coins bekommst du.
So soll erreicht werden, dass negative Ereignisse zeitlich gestreut auftreten und die Kolonie sich dazwischen erholen kann.
Es soll aber **nicht** dafür sorgen, dass keine **negativen Ereignisse** gekauft werden. Diese gehören ja auch zum Spaß dazu.
Daher bleibt dies dir überlassen. Ich bin dir nicht böse.

## Wie benutze ich das Twitch Toolkit?

Du kannst das Twitch Toolkit auf verschiedene Arten nutzen – die wichtigste ist über die
[Befehle]({{- "/commands" | relative_url -}}).
Der wichtigste Befehl ist `!buy`, über den du Dinge aus dem [Shop]({{- "/" | relative_url -}}) kaufen kannst.
Mit `!buy affe 1` kannst du der Kolonie zum Beispiel einen Affen kaufen (Bitte kauf keinen Affen xD). 

Weitere nützliche Befehle sind `!mypawn`, mit dem du verschiedene Informationen über deinen eigenen Pawn abrufen kannst.
Um einen eigenen Pawn zu bekommen kannst du entweder per `!joinqueue` der Warteschlange für die Umbenennug existierender Pawns
beitreten, oder mit `!buy pawn` einen Pawn kaufen. Dieser kommt dann neu in die Kolonie.

{%- if puppeteer -%} <br/>

## Was ist Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) ist eine Mod von **Brrainz**,
die es Zuschauern ermöglicht, ihre **Pawns direkt zu steuern** und verschiedene Informationen über diese grafisch anzuzeigen.
Außerdem leitet sie einige Antworten des Twitch Toolkits an ihre eigene Website weiter, um den Chat übersichtlicher zu halten.

Wenn du also bei **Puppeteer** eingeloggt bist und dich wunderst, warum der Bot dir nicht antwortet,
solltest du zuerst den Reiter **„TT“** auf der Website überprüfen.
{%- endif -%}
