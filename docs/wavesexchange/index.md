---
layout: default
title: WavesExchange
nav_order: 10
has_children: true
---

![WavesExchange Logo](/images/logo-exchange-dark.svg)

**Co to jest WavesExchange?**

Waves Exchange (dawniej Waves DEX) to szybkie i bezpieczne zdecentralizowane środowisko handlowe dla aktywów opartych na Waves i innych wspieranych kryptowalutach, takich jak Bitcoin (BTC), Litecoin (LTC), Ethereum (ETH), Zcash (ZEC) itd.  Obejmuje również szereg fiat stablecoins napędzanych przez Neutrino, takich jak USD Neutrino (USDN), EUR Neutrino (EURN) i GBP Neutrino (GBPN).
Okrzyknięta "najbezpieczniejszą na świecie giełdą kryptowalut" i "najszybszym DEX-em", Waves Exchange nie wymaga od użytkowników przekazania opieki nad ich aktywami podczas handlu i ma wyjątkowo niskie opłaty transakcyjne - na poziomie zaledwie 0,003% za wypełnione zlecenie.
Poza prostymi funkcjami handlu kryptowalutami, Waves Exchange pozwala użytkownikom na ulokowanie różnych aktywów w celu uzyskania zmiennego oprocentowania. Platforma oferuje możliwość zakupu Bitcoin (BTC) i USD Neutrino (USDN) za pomocą karty kredytowej.

<div data-wavescap-widget="" data-design="bright" data-asset-id="WAVES" data-currency="usd-n">
    <div data-wavescap-header="">
        <a data-wavescap-out="link" target="_blank"><img data-wavescap-out="logo"></a> 
        <a data-wavescap-out="link" target="_blank"><span data-wavescap-out="name"></span></a> 
        <span data-wavescap-shortcode="">(<span data-wavescap-out="shortcode"></span>)</span>
    </div>
    <br>
    <div data-wavescap-body="">
        <span data-wavescap-out="price-main"></span>
        <select data-wavescap-select="currency">
            <option value="usd-n">USD</option>
            <option value="eurn">EUR</option>
            <option value="rubn">RUB</option>
            <option value="ngnn">NGN</option>
            <option value="tryn">TRY</option>
            <option value="waves">WAVES</option>
            <option value="btc">BTC</option>
            <option value="eth">ETH</option>
        </select>
        <span data-wavescap-out="price-change-color">(<span data-wavescap-out="price-change"></span>%)</span>
    </div>
    <br>
    <div data-wavescap-footer="">
        <div data-wavescap-cap="">
            <span data-wavescap-cap-title="">Marketcap</span><br>
            <span data-wavescap-out="cap"></span>
        </div>
        <div data-wavescap-vol="">
            <span data-wavescap-vol-title="">DEX Volume</span><br>
            <span data-wavescap-out="vol"></span>
        </div>
        <a data-wavescap-source="" data-wavescap-out="link" target="_blank">by WavesCap</a><!-- Feel free to remove this :-) -->
    </div>
</div>
<style type="text/css">

    [data-wavescap-widget]
    {
        float: right;
        width: auto;
        border: 1px solid grey;
        border-radius: 10px;
        padding: 8px;
        position: relative;
        line-height: 20px;
        font-family: 'Helvetica Neue',Helvetica,Arial,sans-serif;
        min-width: 170px;
        box-sizing: border-box;
    }
    
    [data-wavescap-widget] *,
    [data-wavescap-widget] a:hover
    {
        text-decoration: none;
        color: #222 !important;
    }
    
    [data-wavescap-body]
    {
        margin-top: 6px;
    }
    
    [data-wavescap-source]
    {
        font-size: 8px;
        position: absolute;
        right: 5px;
        top: -2px;
    }
    
    [data-wavescap-shortcode]
    {
        font-size: 9px;
    }
    
    [data-wavescap-cap-title],
    [data-wavescap-vol-title]
    {
        font-size: 13px;
    }
    
    select[data-wavescap-select="currency"]
    {
        -webkit-appearance: none;
        -moz-appearance: none;
        -ms-appearance: none;
        appearance: none;
        outline: 0;
        box-shadow: none;
        border: 0 !important;
        cursor: pointer;
        width: 45px;
        height: 15px;
        font-size: 13px;
        padding: 0 !important;
        margin: 0 !important;
        background: transparent url('data:image/svg+xml;utf8,<svg width="100px" height="100px" viewBox="15 100 200 400" xmlns:xlink="http://www.w3.org/1999/xlink" stroke="black" stroke-opacity="1" fill="black" stroke-width="1" xmlns="http://www.w3.org/2000/svg"><g transform="rotate(-180 100,337) "><path d="M201.375 361.2656 L21.0938 361.2656 L111.2344 205.1719 L201.375 361.2656 Z" stroke="none" /></g></svg>') no-repeat right;
        background-size: contain;
    }
    
    [data-wavescap-select="currency"][data-width-auto="true"]
    {
        width: 63px;
    }
    
    [data-wavescap-footer]
    {
        margin-top: 8px;
    }
    
    [data-wavescap-header] [data-wavescap-out="name"]
    {
        font-size: 26px;
    }
    
    [data-wavescap-widget] > div
    {
        float: left;
        width: 100%;
    }
    
    [data-wavescap-cap],
    [data-wavescap-vol]
    {
        float: left;
        width: 50%;
    }
    
    /* DARK THEME */
    
    [data-wavescap-widget][data-design="dark"] *,
    [data-wavescap-widget][data-design="dark"] a:hover
    {
        color: #ddd !important;
    }
    [data-wavescap-widget][data-design="dark"] [data-wavescap-select="currency"] option
    {
        background: #2b2b2b;
    }
    
    [data-wavescap-widget][data-design="dark"] [data-wavescap-select="currency"]
    {
        background: transparent url('data:image/svg+xml;utf8,<svg width="100px" height="100px" viewBox="15 100 200 400" xmlns:xlink="http://www.w3.org/1999/xlink" stroke="black" stroke-opacity="1" fill="white" stroke-width="1" xmlns="http://www.w3.org/2000/svg"><g transform="rotate(-180 100,337) "><path d="M201.375 361.2656 L21.0938 361.2656 L111.2344 205.1719 L201.375 361.2656 Z" stroke="none" /></g></svg>') no-repeat right;
        background-size: contain;
    }
    
    /* END: DARK THEME */
    
    [data-wavescap-out="price-change-color"][data-wavescap-positive="true"],
    [data-wavescap-out="price-change-color"][data-wavescap-positive="true"] *
    {
        color: #5a81ea !important;
    }
    [data-wavescap-out="price-change-color"][data-wavescap-positive="false"],
    [data-wavescap-out="price-change-color"][data-wavescap-positive="false"] *
    {
        color: #e5494d !important;
    }

</style>

<script type="text/javascript" src="https://wavescap.com/widget/asset.js"></script>

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*
