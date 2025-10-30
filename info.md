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
{%- assign buy = '!buy' -%}
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

Willkommen im Stream von [{{ site.data.social.twitch }}]([https://twitch.tv/{{](https://twitch.tv/{{) site.data.social.twitch }}).
Dieser Stream nutzt die Mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787), um ein interaktives Erlebnis zu ermöglichen.
Die Mod hat viele Funktionen, die selbst für erfahrene Nutzer zunächst etwas kompliziert wirken können – aber diese kurze Anleitung hilft dir, dich schnell zurechtzufinden.

## Was ist das Twitch Toolkit?

Twitch Toolkit ist eine Mod von **hodlhodl**, die es Zuschauern erlaubt, das Spiel auf verschiedene Arten zu beeinflussen.
Das auffälligste Merkmal ist der [Shop]({{- "/" | relative_url -}}), in dem du eine Auswahl an vom Streamer kuratierten Dingen kaufen kannst.
Je nach Kauf erscheinen diese Gegenstände im Spiel oder wirken sich auf das Spielgeschehen aus.
Eine weitere Möglichkeit zur Interaktion bieten die **Abstimmungen** (Polls) der Mod.
Die Auswahlmöglichkeiten in diesen Umfragen hängen stark davon ab, welche Optionen in der Mod aktiviert sind.

## Was sind Coins?

Coins sind die Währung der Mod.
Du kannst dein Guthaben mit dem Befehl `{{ bal }}` anzeigen lassen.

{% if utils == true %}
Dir wird vielleicht auffallen, dass der Balance-Befehl einige neue Emojis enthält.
Falls das der Fall ist, hier eine Übersicht der Bedeutungen:

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

## Wie benutze ich das Twitch Toolkit?

Du kannst das Twitch Toolkit auf verschiedene Arten nutzen – die wichtigste ist über die
[Befehle]({{- "/commands" | relative_url -}}).
Der wichtigste Befehl ist `{{- buy -}}`, über den du Dinge aus dem Shop kaufen kannst.

Weitere nützliche Befehle sind `!mypawn`, mit dem du verschiedene Informationen über deinen eigenen Pawn abrufen kannst.
Wir decken hier nicht jeden Befehl ab – die meisten sind jedoch selbsterklärend oder auf der Seite
[commands]({{- "/commands" | relative_url -}}) näher beschrieben.

{%- if puppeteer -%} <br/>

## Was ist Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) ist eine Mod von **Brrainz**,
die es Zuschauern ermöglicht, ihre **Pawns direkt zu steuern** und verschiedene Informationen über diese grafisch anzuzeigen.
Außerdem leitet sie einige Antworten des Twitch Toolkits an ihre eigene Website weiter, um den Chat übersichtlicher zu halten.

Wenn du also bei **Puppeteer** eingeloggt bist und dich wunderst, warum der Bot dir nicht antwortet,
solltest du zuerst den Reiter **„TT“** auf der Website überprüfen.
{%- endif -%}

# Welcome

Welcome to [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }})'s stream.
This stream uses the mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) to provide an
interactive experience. There's a lot to the mod that may seem complicated to even more experienced
users, but this short guide will help you get the hang of things.

## What is Twitch Toolkit?

Twitch Toolkit is a mod by hodlhodl that allows viewers to affect the game in a number of ways. The
most prominent is its [store]({{- "/" | relative_url -}}), which allows you to purchase a number of
things the streamer curated. Depending on the purchase, these things appear in-game or affect the
game in some way. Another way viewers can interact with the game is through the mod's polls. The
choices in these polls depend heavily on what's enabled in the mod.

## What Are Coins?

Coins are the mod's currency. You can view your balance by using the `{{ bal }}` command. 

{% if utils == true %}
You'll notice the balance command may have some new emojis. If that's the case, here is an overview
of the emojis as follows:

- 💰 represents the amount of coins you current have.
- ⚖ represents your current karma.
- 📈 represents the amount of coins you gain everytime the mod awards coins.
- 📉 represents the amount of coins you lose everytime to mod awards coins.

{% endif %}


{%- if lootboxes == true -%}
You'll also notice that you'll get a message from the bot about a lootbox. You can open this lootbox
by using the `!openlootbox` command, as well as check the number of lootboxes you have with `!lootboxes`.
You'll always get a new lootbox everyday.
{%- endif -%}


<br/>
## What is Karma?

Karma is a system in the mod that tries to limit the amount of negative events a viewer can purchase at
one time. This system works by directly modifying that amount of coins viewers get everytime the mod
awards coins. This means that the lower you karma is, the lower your coin gain is. The hope is that
negative events get spread out more so the colony can recover.

## How Do I Use Twitch Toolkit?

You can use Twitch Toolkit in a number of ways -- the most prominent way is through its
[commands]({{- "/commands" | relative_url -}}). The more important command is the `{{- buy -}}`
command, which is the mods entry point into purchasing things from the store. Other notable commands
are the `!mypawn` commands, which allow you see various information about your pawn. We won't cover
every command here, but most commands should generally be self-descriptive or have a description of
what they do on the [commands]({{- "/commands" | relative_url -}}) page.


{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
