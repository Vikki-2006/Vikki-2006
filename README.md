<img width="1280" height="640" alt="banner (4)" src="https://github.com/user-attachments/assets/fd9363ef-f442-4554-81af-4a002a29dedd" />
<svg width="1280" height="640" viewBox="0 0 1280 640" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<defs>

  <!-- drafting grid -->
  <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
    <path d="M40 0H0V40" fill="none" stroke="#294B72" stroke-width="0.6" opacity="0.55"/>
  </pattern>
  <pattern id="gridMajor" width="200" height="200" patternUnits="userSpaceOnUse">
    <path d="M200 0H0V200" fill="none" stroke="#3A5E8C" stroke-width="0.9" opacity="0.5"/>
  </pattern>

  <!-- paper grain -->
  <filter id="grain">
    <feTurbulence type="fractalNoise" baseFrequency="0.85" numOctaves="2" stitchTiles="stitch" result="noise">
      <animate attributeName="baseFrequency" values="0.85;0.9;0.85" dur="14s" repeatCount="indefinite"/>
    </feTurbulence>
    <feColorMatrix in="noise" type="matrix"
      values="0 0 0 0 0.62
              0 0 0 0 0.75
              0 0 0 0 1
              0 0 0 0.045 0"/>
  </filter>

  <!-- hatch fill used inside the letterforms -->
  <pattern id="hatch" width="7" height="7" patternTransform="rotate(45)" patternUnits="userSpaceOnUse">
    <rect width="7" height="7" fill="#0B1D39"/>
    <line x1="0" y1="0" x2="0" y2="7" stroke="#7FB7FF" stroke-width="1.3" opacity="0.85"/>
  </pattern>

  <radialGradient id="vignette" cx="50%" cy="45%" r="75%">
    <stop offset="60%" stop-color="#0B1D39" stop-opacity="0"/>
    <stop offset="100%" stop-color="#050E1E" stop-opacity="0.55"/>
  </radialGradient>

  <clipPath id="frameClip">
    <rect x="18" y="18" width="1244" height="604" rx="6"/>
  </clipPath>

  <style>
    <![CDATA[
    text { font-family: 'Segoe UI', Arial, Helvetica, sans-serif; }
    .name-face { font-family: 'Bahnschrift', 'DIN Alternate', 'DIN Condensed', 'Eurostile', 'Arial Narrow', 'Segoe UI', sans-serif; }

    .grid-layer{ animation: gridFade 4s ease-out forwards; }
    @keyframes gridFade{ 0%{opacity:0;} 100%{opacity:1;} }

    .grid-drift{ animation: drift 22s ease-in-out infinite; }
    @keyframes drift{
      0%,100%{ transform: translate(0px,0px); }
      50%{ transform: translate(3px,2px); }
    }

    .rotate-slow{ animation: rotateSlow 90s linear infinite; transform-box: fill-box; transform-origin: center; }
    .rotate-slow-rev{ animation: rotateSlowRev 70s linear infinite; transform-box: fill-box; transform-origin: center; }
    @keyframes rotateSlow{ from{ transform: rotate(0deg);} to{ transform: rotate(360deg);} }
    @keyframes rotateSlowRev{ from{ transform: rotate(360deg);} to{ transform: rotate(0deg);} }

    .pulse{ animation: pulse 3.4s ease-in-out infinite; transform-box: fill-box; transform-origin: center; }
    @keyframes pulse{
      0%,100%{ opacity:0.35; transform: scale(1); }
      50%{ opacity:0.95; transform: scale(1.35); }
    }

    .blink{ animation: blink 2.6s ease-in-out infinite; }
    .blink2{ animation: blink 2.6s ease-in-out infinite 1.1s; }
    .blink3{ animation: blink 3.2s ease-in-out infinite 0.5s; }
    @keyframes blink{
      0%,100%{ opacity:0.15; }
      50%{ opacity:1; }
    }

    .float1{ animation: float1 12s ease-in-out infinite; }
    .float2{ animation: float2 15s ease-in-out infinite; }
    .float3{ animation: float3 18s ease-in-out infinite; }
    @keyframes float1{ 0%,100%{ transform: translate(0,0); opacity:0.25;} 50%{ transform: translate(6px,-10px); opacity:0.7;} }
    @keyframes float2{ 0%,100%{ transform: translate(0,0); opacity:0.2;} 50%{ transform: translate(-8px,-6px); opacity:0.6;} }
    @keyframes float3{ 0%,100%{ transform: translate(0,0); opacity:0.3;} 50%{ transform: translate(5px,8px); opacity:0.75;} }

    .dash-draw{ stroke-dasharray: 6 5; animation: dashMove 3s linear infinite; }
    @keyframes dashMove{ to{ stroke-dashoffset: -220; } }

    .arrow-seq > *{ opacity:0; animation: arrowIn 6s ease-in-out infinite; }
    .arrow-seq > *:nth-child(1){ animation-delay: 0s; }
    .arrow-seq > *:nth-child(2){ animation-delay: 0.7s; }
    .arrow-seq > *:nth-child(3){ animation-delay: 1.4s; }
    .arrow-seq > *:nth-child(4){ animation-delay: 2.1s; }
    @keyframes arrowIn{
      0%{ opacity:0; }
      8%{ opacity:1; }
      75%{ opacity:1; }
      92%{ opacity:0; }
      100%{ opacity:0; }
    }

    .grain-breathe{ animation: grainBreathe 10s ease-in-out infinite; }
    @keyframes grainBreathe{
      0%,100%{ opacity:0.75; }
      50%{ opacity:1; }
    }

    .cross-blink circle{ animation: blink 4s ease-in-out infinite; }
    ]]>
  </style>
</defs>

<!-- BASE -->
<rect width="1280" height="640" fill="#0B1D39"/>
<rect width="1280" height="640" filter="url(#grain)" class="grain-breathe"/>
<g class="grid-layer">
  <g class="grid-drift">
    <rect width="1280" height="640" fill="url(#grid)"/>
    <rect width="1280" height="640" fill="url(#gridMajor)"/>
  </g>
</g>
<rect width="1280" height="640" fill="url(#vignette)"/>

<!-- outer drafting frame -->
<rect x="18" y="18" width="1244" height="604" rx="6" fill="none" stroke="#3A5E8C" stroke-width="1.2"/>
<rect x="30" y="30" width="1220" height="580" rx="4" fill="none" stroke="#294B72" stroke-width="0.8" stroke-dasharray="2 6"/>

<!-- corner tick marks -->
<g stroke="#7FB7FF" stroke-width="1.2" opacity="0.8">
  <path d="M18 46 V18 H46"/>
  <path d="M1234 18 H1262 V46"/>
  <path d="M1262 594 V622 H1234"/>
  <path d="M46 622 H18 V594"/>
</g>

<g clip-path="url(#frameClip)">

  <!-- top dimension bracket -->
  <g transform="translate(490,54)" font-size="12" fill="#D9E8FF" letter-spacing="2" opacity="0.85">
    <line x1="0" y1="10" x2="0" y2="0" stroke="#7FB7FF" stroke-width="1"/>
    <line x1="300" y1="10" x2="300" y2="0" stroke="#7FB7FF" stroke-width="1"/>
    <line x1="0" y1="6" x2="300" y2="6" stroke="#7FB7FF" stroke-width="1"/>
    <path d="M0 6 L10 3 L10 9 Z" fill="#7FB7FF"/>
    <path d="M300 6 L290 3 L290 9 Z" fill="#7FB7FF"/>
    <text x="150" y="-4" text-anchor="middle" font-family="Consolas, monospace">1280.0</text>
  </g>

  <!-- left dimension bracket -->
  <g transform="translate(46,190)" font-size="12" fill="#D9E8FF" opacity="0.85">
    <line x1="0" y1="0" x2="10" y2="0" stroke="#7FB7FF" stroke-width="1"/>
    <line x1="0" y1="260" x2="10" y2="260" stroke="#7FB7FF" stroke-width="1"/>
    <line x1="4" y1="0" x2="4" y2="260" stroke="#7FB7FF" stroke-width="1"/>
    <path d="M4 0 L1 10 L7 10 Z" fill="#7FB7FF"/>
    <path d="M4 260 L1 250 L7 250 Z" fill="#7FB7FF"/>
    <text x="-8" y="134" text-anchor="middle" font-family="Consolas, monospace" transform="rotate(-90 -8 134)">640.0</text>
  </g>

  <!-- right side ticks -->
  <g transform="translate(1210,190)" font-size="11" fill="#9CBBEA" opacity="0.7" font-family="Consolas, monospace">
    <text x="0" y="0">R 45</text>
    <text x="0" y="260">Ø 12</text>
  </g>

  <!-- top-left gear motif -->
  <g transform="translate(110,120)" opacity="0.55">
    <g class="rotate-slow" stroke="#7FB7FF" stroke-width="1.3" fill="none">
      <circle r="58"/>
      <circle r="40"/>
      <circle r="6" fill="#7FB7FF" stroke="none"/>
      <g id="teeth">
        <path d="M0,-58 L0,-72 M41,-41 L51,-51 M58,0 L72,0 M41,41 L51,51 M0,58 L0,72 M-41,41 L-51,51 M-58,0 L-72,0 M-41,-41 L-51,-51"/>
      </g>
    </g>
    <g class="rotate-slow-rev" stroke="#D9E8FF" stroke-width="0.8" fill="none" opacity="0.6">
      <circle r="24" stroke-dasharray="3 4"/>
    </g>
  </g>

  <!-- top-right isometric cube -->
  <g transform="translate(1120,110)" opacity="0.6" stroke="#7FB7FF" stroke-width="1.1" fill="none">
    <path d="M0,30 L45,5 L90,30 L45,55 Z"/>
    <path d="M0,30 L0,80 L45,105 L45,55 Z"/>
    <path d="M90,30 L90,80 L45,105 L45,55 Z"/>
    <path d="M0,30 L45,55 L90,30" stroke-dasharray="2 3" opacity="0.7"/>
    <g font-size="10" fill="#9CBBEA" stroke="none" font-family="Consolas, monospace" opacity="0.85">
      <text x="14" y="12">45</text>
      <text x="-16" y="60">45</text>
      <text x="70" y="100">45</text>
    </g>
  </g>

  <!-- bottom-left circuit sketch -->
  <g transform="translate(70,470)" opacity="0.55" stroke="#7FB7FF" stroke-width="1.1" fill="none">
    <circle cx="0" cy="0" r="3.5" fill="#0B1D39"/>
    <path d="M0,0 H60 V30 H120"/>
    <circle cx="120" cy="30" r="3.5" fill="#0B1D39"/>
    <path d="M0,0 V40 H50 V70 H130"/>
    <rect x="50" y="55" width="12" height="12"/>
    <circle cx="130" cy="70" r="3.5" fill="#0B1D39"/>
    <path d="M0,40 V85 H90"/>
    <rect x="90" y="78" width="14" height="14"/>
  </g>

  <!-- bottom-right concentric drafting circles -->
  <g transform="translate(1130,520)" opacity="0.55">
    <g class="rotate-slow-rev" stroke="#7FB7FF" stroke-width="1" fill="none">
      <circle r="70" stroke-dasharray="4 5"/>
    </g>
    <g class="rotate-slow" stroke="#D9E8FF" stroke-width="0.9" fill="none">
      <circle r="46"/>
      <circle r="46" stroke-dasharray="1 6"/>
    </g>
    <line x1="-70" y1="0" x2="70" y2="0" stroke="#294B72" stroke-width="0.8"/>
    <line x1="0" y1="-70" x2="0" y2="70" stroke="#294B72" stroke-width="0.8"/>
    <text x="0" y="-80" text-anchor="middle" font-size="11" fill="#9CBBEA" font-family="Consolas, monospace">SCALE 1:1</text>
  </g>

  <!-- scattered coordinate markers -->
  <g stroke="#F2F6FF" stroke-width="1" fill="none">
    <g class="cross-blink" transform="translate(330,110)">
      <line x1="-7" y1="0" x2="7" y2="0"/><line x1="0" y1="-7" x2="0" y2="7"/>
      <circle cx="0" cy="0" r="2.2" fill="#F2F6FF" stroke="none"/>
    </g>
    <g class="cross-blink" transform="translate(950,530)">
      <line x1="-7" y1="0" x2="7" y2="0"/><line x1="0" y1="-7" x2="0" y2="7"/>
      <circle cx="0" cy="0" r="2.2" fill="#F2F6FF" stroke="none"/>
    </g>
    <g class="cross-blink" transform="translate(220,340)">
      <line x1="-7" y1="0" x2="7" y2="0"/><line x1="0" y1="-7" x2="0" y2="7"/>
      <circle cx="0" cy="0" r="2.2" fill="#F2F6FF" stroke="none"/>
    </g>
  </g>

  <!-- soft pulsing drafting dots -->
  <circle class="pulse" cx="640" cy="228" r="3" fill="#7FB7FF"/>
  <circle class="pulse" cx="380" cy="470" r="2.4" fill="#D9E8FF" style="animation-delay:1s"/>
  <circle class="pulse" cx="900" cy="470" r="2.4" fill="#D9E8FF" style="animation-delay:1.8s"/>

  <!-- dimension arrows appearing one by one -->
  <g class="arrow-seq" font-family="Consolas, monospace" font-size="10" fill="#9CBBEA">
    <g transform="translate(150,590)"><line x1="0" y1="0" x2="70" y2="0" stroke="#7FB7FF"/><path d="M70,0 L62,-3 L62,3 Z" fill="#7FB7FF"/><text x="0" y="-6">14.0</text></g>
    <g transform="translate(1060,60)"><line x1="0" y1="0" x2="0" y2="50" stroke="#7FB7FF"/><path d="M0,50 L-3,42 L3,42 Z" fill="#7FB7FF"/><text x="6" y="30">6.0</text></g>
    <g transform="translate(250,230)"><line x1="0" y1="0" x2="0" y2="-40" stroke="#7FB7FF"/><path d="M0,-40 L-3,-32 L3,-32 Z" fill="#7FB7FF"/></g>
    <g transform="translate(1000,400)"><line x1="0" y1="0" x2="40" y2="0" stroke="#7FB7FF"/><path d="M40,0 L32,-3 L32,3 Z" fill="#7FB7FF"/></g>
  </g>

  <!-- floating blueprint dust -->
  <g fill="#D9E8FF">
    <circle class="float1" cx="220" cy="240" r="1.4" opacity="0.4"/>
    <circle class="float2" cx="1040" cy="260" r="1.2" opacity="0.4"/>
    <circle class="float3" cx="640" cy="140" r="1.3" opacity="0.35"/>
    <circle class="float1" cx="820" cy="480" r="1.1" opacity="0.4" style="animation-delay:2s"/>
    <circle class="float2" cx="440" cy="500" r="1.5" opacity="0.35" style="animation-delay:3s"/>
    <circle class="float3" cx="960" cy="150" r="1.2" opacity="0.4" style="animation-delay:1.4s"/>
  </g>

  <!-- ============ CENTERPIECE ============ -->

  <!-- construction guide box + centerline -->
  <g stroke="#3A6295" stroke-width="1" opacity="0.75">
    <line x1="60" y1="320" x2="1220" y2="320" class="dash-draw"/>
    <circle cx="640" cy="320" r="4.5" fill="#0B1D39" stroke="#F2F6FF" stroke-width="1.3"/>
    <circle cx="640" cy="320" r="4.5" fill="#F2F6FF" opacity="0.9"/>
    <rect x="150" y="248" width="980" height="120" fill="none" stroke-dasharray="3 5" opacity="0.8"/>
    <line x1="150" y1="248" x2="150" y2="368" stroke-dasharray="2 4" opacity="0.6"/>
    <line x1="1130" y1="248" x2="1130" y2="368" stroke-dasharray="2 4" opacity="0.6"/>
  </g>

  <!-- construction guide pass: light pencil layer sitting permanently behind the final letterforms -->
  <text x="640" y="345" text-anchor="middle" class="name-face"
        font-size="92" font-weight="700" letter-spacing="7"
        fill="none" stroke="#3A6295" stroke-width="1" opacity="0.45">
    VIGNESHWARAN S
  </text>

  <!-- hatch fill and crisp final outline: fully static, always at full opacity, no glow or sweep -->
  <text x="640" y="345" text-anchor="middle" class="name-face"
        font-size="92" font-weight="700" letter-spacing="7"
        fill="url(#hatch)">
    VIGNESHWARAN S
  </text>
  <text x="640" y="345" text-anchor="middle" class="name-face"
        font-size="92" font-weight="700" letter-spacing="7"
        fill="none" stroke="#F2F6FF" stroke-width="1.8">
    VIGNESHWARAN S
  </text>

  <!-- engineering annotations around the name: corner brackets, baseline + dimension references -->
  <g stroke="#7FB7FF" stroke-width="1" opacity="0.75" fill="none">
    <path d="M150 248 h18 M150 248 v18"/>
    <path d="M1130 248 h-18 M1130 248 v18"/>
    <path d="M150 368 h18 M150 368 v-18"/>
    <path d="M1130 368 h-18 M1130 368 v-18"/>
  </g>
  <g stroke="#3A6295" stroke-width="0.8" stroke-dasharray="1 5" opacity="0.65">
    <line x1="640" y1="248" x2="640" y2="368"/>
  </g>
  <g font-family="Consolas, monospace" font-size="9.5" fill="#5E82AE" letter-spacing="1.5" opacity="0.8">
    <text x="150" y="238">TYP.</text>
    <text x="1130" y="238" text-anchor="end">NAME PLATE</text>
    <text x="1112" y="323" text-anchor="end">BASELINE</text>
  </g>
  <g stroke="#5E82AE" stroke-width="0.8" opacity="0.7">
    <line x1="1030" y1="323" x2="1104" y2="323"/>
  </g>

  <!-- quote -->
  <text x="640" y="412" text-anchor="middle" font-size="19" letter-spacing="3"
        fill="#D9E8FF" font-family="Consolas, monospace">
    "Designing solutions before writing code."
  </text>

  <!-- small annotation rule under quote -->
  <g font-family="Consolas, monospace" font-size="10.5" fill="#5E82AE" letter-spacing="2" opacity="0.8" text-anchor="middle">
    <text x="640" y="444">REV A &#8226; SHEET 1/1 &#8226; SCALE NOT TO SCALE</text>
  </g>

  <!-- GitHub signature label: blueprint title-block style, static, subtle -->
  <g transform="translate(640,486)" text-anchor="middle">
    <line x1="-90" y1="-28" x2="90" y2="-28" stroke="#294B72" stroke-width="0.9" opacity="0.8"/>

    <!-- small title-block label -->
    <text x="0" y="-13" font-family="Consolas, monospace" font-size="9.5" letter-spacing="4"
          fill="#5E82AE" opacity="0.85">GITHUB</text>

    <!-- icon + username row, precisely centered and vertically aligned -->
    <g transform="translate(-57,7)">
      <!-- official octocat mark, 16x16, vertically centered on the username's cap-height -->
      <path transform="translate(0,-13)"
            d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
            fill="#D9E8FF" opacity="0.92"/>
      <text x="26" y="0" text-anchor="start" font-family="Consolas, monospace" font-size="14.5"
            letter-spacing="1" fill="#9CBBEA">Vikki-2006</text>
    </g>
  </g>


</g>
</svg>
