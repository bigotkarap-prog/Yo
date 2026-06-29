1000	
  1001	        .env-flap {
  1002	            position: absolute;
  1003	            top: 0;
  1004	            left: 0;
  1005	            right: 0;
  1006	            height: 130px;
  1007	            background: linear-gradient(175deg, #f5d5ce 0%, #eec5bc 50%, #e8b8ae 100%);
  1008	            border-radius: 14px 14px 0 0;
  1009	            clip-path: polygon(0 0, 100% 0, 50% 78%);
  1010	            border: 1.2px solid rgba(210, 155, 145, 0.5);
  1011	            transform-origin: top center;
  1012	            transform: rotateX(0deg);
  1013	            transition: transform 1.0s cubic-bezier(0.25, 0.85, 0.25, 1);
  1014	            will-change: transform;
  1015	            backface-visibility: hidden;
  1016	            box-shadow: inset 0 -8px 20px rgba(180, 110, 100, 0.12);
  1017	        }
  1018	
  1019	        .env-flap::before {
  1020	            content: '';
  1021	            position: absolute;
  1022	            top: 0;
  1023	            left: 0;
  1024	            right: 0;
  1025	            height: 28px;
  1026	            background: linear-gradient(to bottom, rgba(255, 255, 255, 0.35) 0%, transparent 100%);
  1027	            border-radius: 14px 14px 0 0;
  1028	            pointer-events: none;
  1029	        }
  1030	
  1031	        .env-flap::after {
  1032	            content: '';
  1033	            position: absolute;
  1034	            inset: 0;
  1035	            background: linear-gradient(175deg, rgba(0, 0, 0, 0.0) 0%, rgba(140, 80, 70, 0.10) 100%);
  1036	            transition: opacity 1.0s ease;
  1037	            pointer-events: none;
  1038	        }
  1039	
  1040	        .envelope-wrapper.open .env-flap {
  1041	            transform: rotateX(-178deg);
  1042	        }
  1043	
  1044	        .envelope-wrapper.open .env-flap::after {
  1045	            opacity: 0;
  1046	        }
  1047	
  1048	        .env-seal {
  1049	            position: absolute;
  1050	            top: calc(130px * 0.78 - 20px);
  1051	            left: 50%;
  1052	            transform: translateX(-50%);
  1053	            font-size: 2rem;
  1054	            z-index: 7;
  1055	            pointer-events: none;
  1056	            transition:
  1057	                opacity 0.3s 0.05s ease,
  1058	                transform 0.3s 0.05s cubic-bezier(0.34, 1.2, 0.64, 1);
  1059	            will-change: opacity, transform;
  1060	            filter: drop-shadow(0 2px 6px rgba(190, 130, 120, 0.3));
  1061	        }
  1062	
  1063	        .envelope-wrapper.open .env-seal {
  1064	            opacity: 0;
  1065	            transform: translateX(-50%) scale(0.5) translateY(-6px);
  1066	        }
  1067	
  1068	        .envelope-label {
  1069	            font-family: 'Cormorant Garamond', Georgia, serif;
  1070	            font-style: italic;
  1071	            font-weight: 500;
  1072	            font-size: 1.25rem;
  1073	            color: rgba(160, 110, 100, 0.75);
  1074	            letter-spacing: 0.05em;
  1075	            text-align: center;
  1076	            animation: labelBreath 3s ease-in-out infinite;
  1077	        }
  1078	
  1079	        .envelope-label .sparkle-gold {
  1080	            color: #d4a843;
  1081	            font-style: normal;
  1082	            font-size: 0.9rem;
  1083	        }
  1084	
  1085	        @keyframes labelBreath {
  1086	            0%, 100% { opacity: 0.7; }
  1087	            50%      { opacity: 1.0; }
  1088	        }
  1089	
  1090	        .envelope-click-hint {
  1091	            display: none;
  1092	        }
  1093	
  1094	        @keyframes flowerRain {
  1095	            0%   { transform: translateY(-60px) rotate(-10deg) scale(0.6); opacity: 0; }
  1096	            5%   { opacity: 1; }
  1097	            90%  { opacity: 0.9; }
  1098	            100% { transform: translateY(110vh) rotate(20deg) scale(0.9); opacity: 0; }
  1099	        }
  1100	
  1101	        /* ============================================
  1102	           RESPONSIVE
  1103	           ============================================ */
  1104	        @media (max-width: 600px) {
  1105	            h1           { font-size: 2rem; }
  1106	            .name        { font-size: 3rem; }
  1107	            .bouquet     { font-size: 3.5rem; }
  1108	            .main-cake   { font-size: 3.5rem; }
  1109	            .message-card { margin: 15px 10px; padding: 20px; }
  1110	            .bunny-art   { font-size: 0.9rem; padding: 10px 15px; }
  1111	            .message-text { font-size: 1.1rem; }
  1112	        }
  1113	    </style>
  1114	</head>
  1115	<body>
  1116	    <!-- ============================================
  1117	         BACKGROUND
  1118	         ============================================ -->
  1119	    <div class="ocean-bg"></div>
  1120	
  1121	    <!-- Waves -->
  1122	    <div class="wave wave-1"></div>
  1123	    <div class="wave wave-2"></div>
  1124	    <div class="wave wave-3"></div>
  1125	
  1126	    <!-- Clouds -->
  1127	    <div class="cloud cloud-1"></div>
  1128	    <div class="cloud cloud-2"></div>
  1129	    <div class="cloud cloud-3"></div>
  1130	
  1131	    <!-- ============================================
  1132	         ENVELOPE OVERLAY
  1133	         ============================================ -->
  1134	    <div class="envelope-overlay" id="envelopeOverlay">
  1135	        <div class="envelope-bob" id="envelopeBob">
  1136	            <div class="envelope-wrapper" id="envelopeWrapper">
  1137	                <div class="env-body"></div>
  1138	                <div class="env-letter">
  1139	                    <div class="env-letter-inner">
  1140	                        <div class="env-letter-emoji">🎂🌷</div>
  1141	                        <div class="env-letter-text">For Leecha ✨</div>
  1142	                    </div>
  1143	                </div>
  1144	                <div class="env-flap-container">
  1145	                    <div class="env-flap" id="envFlap"></div>
  1146	                </div>
  1147	                <div class="env-seal" id="envSeal">💌</div>
  1148	            </div>
  1149	        </div>
  1150	        <div class="envelope-label">A surprise awaits...</div>
  1151	        <div class="envelope-click-hint">Click to open 💌</div>
  1152	    </div>
  1153	
  1154	    <!-- ============================================
  1155	         OPENING OVERLAY
  1156	         ============================================ -->
  1157	    <div class="opening-overlay" id="openingOverlay">
  1158	        <div class="opening-bubble" id="openingBubble">
  1159	            <div class="ponyo-cake">🎂</div>
  1160	        </div>
  1161	        <div class="candles-row">
  1162	            <div class="ponyo-candle">
  1163	                <div class="ponyo-flame" id="oFlame1"></div>
  1164	                <div class="candle-body"></div>
  1165	            </div>
  1166	            <div class="ponyo-candle">
  1167	                <div class="ponyo-flame" id="oFlame2"></div>
  1168	                <div class="candle-body"></div>
  1169	            </div>
  1170	            <div class="ponyo-candle">
  1171	                <div class="ponyo-flame" id="oFlame3"></div>
  1172	                <div class="candle-body"></div>
  1173	            </div>
  1174	        </div>
  1175	        <div class="opening-text">Make a wish, Leecha...</div>
  1176	        <div class="hint-text">Blow the candles or click the bubble ✨</div>
  1177	    </div>
  1178	
  1179	    <!-- ============================================
  1180	         MAIN CONTENT
  1181	         ============================================ -->
  1182	    <div class="container" id="mainContent">
  1183	        <h1>Happy Birthday</h1>
  1184	        <div class="name">Leecha 🥳🎉</div>
  1185	
  1186	        <!-- Bunny ASCII Art -->
  1187	        <div class="bunny-art">(\_(/)
  1188	(• .•)
  1189	(&gt;🌷</div>
  1190	
  1191	        <!-- Bouquet -->
  1192	        <div class="bouquet-container" id="bouquet" onclick="shakeBouquet()">
  1193	            <div class="bouquet">💐</div>
  1194	            <div class="bouquet-ribbon"></div>
  1195	        </div>
  1196	
  1197	        <!-- Cake -->
  1198	        <div class="cake-wrapper" id="cakeWrapper" onclick="blowMainCandles()">
  1199	            <div class="main-cake" id="mainCake">🎂</div>
  1200	            <div class="main-candles">
  1201	                <div class="ponyo-candle">
  1202	                    <div class="ponyo-flame" id="mFlame1"></div>
  1203	                    <div class="candle-body"></div>
  1204	                </div>
  1205	                <div class="ponyo-candle">
  1206	                    <div class="ponyo-flame" id="mFlame2"></div>
  1207	                    <div class="candle-body"></div>
  1208	                </div>
  1209	                <div class="ponyo-candle">
  1210	                    <div class="ponyo-flame" id="mFlame3"></div>
  1211	                    <div class="candle-body"></div>
  1212	                </div>
  1213	            </div>
  1214	        </div>
  1215	
  1216	        <!-- Message -->
  1217	        <div class="message-card">
  1218	            <div class="message-text">
  1219	                Wishing you a day as bright and wonderful as you are —
  1220	                may this year bring you joy, laughter, and all the little
  1221	                things that make you smile.
  1222	            </div>
  1223	        </div>
  1224	
  1225	        <button class="btn" onclick="celebrate()">click here to celebrate 🌷</button>
  1226	    </div>
  1227	
  1228	    <!-- ============================================
  1229	         EASTER EGG
  1230	         ============================================ -->
  1231	    <div class="easter-egg" id="easterEgg">🐡</div>
  1232	    <div class="secret-toast" id="secretToast">🍖 Ponyo found you! She just wants ham! 🐟✨</div>
  1233	
  1234	    <!-- ============================================
  1235	         SCRIPTS
  1236	         ============================================ -->
  1237	    <script>
  1238	        /* ============================================
  1239	           CONSTANTS
  1240	           ============================================ */
  1241	        const ponyoColors  = ['#FF6B6B', '#4ECDC4', '#FFD93D', '#FF8E8E', '#95E1D3', '#F38181', '#AA96DA', '#FCBAD3'];
  1242	        const fishEmojis   = ['🐟', '🐠', '🐡', '🦈', '🐬', '🐳', '🦑', '🐙'];
  1243	        const flowerEmojis = ['🌷', '🪷', '🌷', '🪷', '🌷', '🪷', '🌷'];
  1244	
  1245	        // Store interval IDs for cleanup
  1246	        let intervals = [];
  1247	
  1248	        /* ============================================
  1249	           BUBBLES
  1250	           ============================================ */
  1251	        function createBubble() {
  1252	            const bubble = document.createElement('div');
  1253	            bubble.className = 'bubble';
  1254	            const size = Math.random() * 40 + 15;
  1255	            bubble.style.width  = size + 'px';
  1256	            bubble.style.height = size + 'px';
  1257	            bubble.style.left   = Math.random() * 100 + 'vw';
  1258	            bubble.style.animationDuration = (Math.random() * 8 + 6) + 's';
  1259	            bubble.style.animationDelay    = Math.random() * 5 + 's';
  1260	            document.body.appendChild(bubble);
  1261	            setTimeout(() => bubble.remove(), 15000);
  1262	        }
  1263	
  1264	        /* ============================================
  1265	           WATER BALLOONS
  1266	           ============================================ */
  1267	        function createWaterBalloon() {
  1268	            const balloon = document.createElement('div');
  1269	            balloon.className = 'water-balloon';
  1270	            const size = Math.random() * 35 + 25;
  1271	            balloon.style.width  = size + 'px';
  1272	            balloon.style.height = size * 1.1 + 'px';
  1273	            balloon.style.left   = Math.random() * 90 + 5 + 'vw';
  1274	            balloon.style.background = `radial-gradient(
  1275	                circle at 35% 35%,
  1276	                ${ponyoColors[Math.floor(Math.random() * ponyoColors.length)]} 0%,
  1277	                ${ponyoColors[Math.floor(Math.random() * ponyoColors.length)]}80 100%
  1278	            )`;
  1279	            balloon.style.animationDuration = (Math.random() * 4 + 5) + 's';
  1280	            balloon.style.animationDelay    = Math.random() * 3 + 's';
  1281	            balloon.addEventListener('click', (e) => {
  1282	                e.stopPropagation();
  1283	                popBalloon(balloon, e.clientX, e.clientY);
  1284	            });
  1285	            document.body.appendChild(balloon);
  1286	            setTimeout(() => { if (balloon.parentNode) balloon.remove(); }, 10000);
  1287	        }
  1288	
  1289	        function popBalloon(element, x, y) {
  1290	            element.classList.add('pop');
  1291	            for (let i = 0; i < 8; i++) {
  1292	                const splash = document.createElement('div');
  1293	                splash.className = 'splash';
  1294	                splash.style.left   = x + 'px';
  1295	                splash.style.top    = y + 'px';
  1296	                splash.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
  1297	                splash.style.setProperty('--tx', (Math.random() * 100 - 50) + 'px');
  1298	                splash.style.setProperty('--ty', (Math.random() * 80 + 20) + 'px');
  1299	                document.body.appendChild(splash);
  1300	                setTimeout(() => splash.remove(), 600);
  1301	            }
  1302	            setTimeout(() => element.remove(), 300);
  1303	        }
  1304	
  1305	        /* ============================================
  1306	           FISH
  1307	           ============================================ */
  1308	        function createFish() {
  1309	            const fish = document.createElement('div');
  1310	            fish.className = 'fish';
  1311	            fish.textContent = fishEmojis[Math.floor(Math.random() * fishEmojis.length)];
  1312	            fish.style.top              = Math.random() * 80 + 10 + '%';
  1313	            fish.style.animationDuration = (Math.random() * 15 + 10) + 's';
  1314	            fish.style.animationDelay    = Math.random() * 10 + 's';
  1315	            fish.style.fontSize          = (Math.random() * 1.5 + 1.5) + 'rem';
  1316	            document.body.appendChild(fish);
  1317	            setTimeout(() => fish.remove(), 25000);
  1318	        }
  1319	
  1320	        /* ============================================
  1321	           SPARKLES
  1322	           ============================================ */
  1323	        function createSparkle() {
  1324	            const sparkle = document.createElement('div');
  1325	            sparkle.className = 'sparkle';
  1326	            sparkle.style.left = Math.random() * 100 + 'vw';
  1327	            sparkle.style.top  = Math.random() * 100 + 'vh';
  1328	            sparkle.style.animationDelay = Math.random() * 2 + 's';
  1329	            document.body.appendChild(sparkle);
  1330	            setTimeout(() => sparkle.remove(), 3000);
  1331	        }
  1332	
  1333	        /* ============================================
  1334	           STARFISH
  1335	           ============================================ */
  1336	        function createStarfish() {
  1337	            const starfish = document.createElement('div');
  1338	            starfish.className = 'starfish';
  1339	            starfish.textContent = '⭐';
  1340	            starfish.style.left              = Math.random() * 90 + 5 + '%';
  1341	            starfish.style.top               = Math.random() * 90 + 5 + '%';
  1342	            starfish.style.animationDelay    = Math.random() * 5 + 's';
  1343	            starfish.style.animationDuration = (Math.random() * 3 + 4) + 's';
  1344	            document.body.appendChild(starfish);
  1345	        }
  1346	
  1347	        /* ============================================
  1348	           CONFETTI
  1349	           ============================================ */
  1350	        function createConfetti() {
  1351	            const confetti = document.createElement('div');
  1352	            confetti.className = 'confetti';
  1353	            confetti.style.left = Math.random() * 100 + 'vw';
  1354	            confetti.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
  1355	            confetti.style.animationDuration = (Math.random() * 3 + 2) + 's';
  1356	            confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
  1357	            document.body.appendChild(confetti);
  1358	            setTimeout(() => confetti.remove(), 6000);
  1359	        }
  1360	
  1361	        /* ============================================
  1362	           MAGIC PARTICLES
  1363	           ============================================ */
  1364	        function createMagicParticle(x, y) {
  1365	            const particle = document.createElement('div');
  1366	            particle.className = 'magic-particle';
  1367	            particle.style.left = x + 'px';
  1368	            particle.style.top  = y + 'px';
  1369	            particle.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
  1370	            particle.style.setProperty('--mx', (Math.random() * 200 - 100) + 'px');
  1371	            particle.style.setProperty('--my', (Math.random() * 200 - 100) + 'px');
  1372	            document.body.appendChild(particle);
  1373	            setTimeout(() => particle.remove(), 3000);
  1374	        }
  1375	
  1376	        /* ============================================
  1377	           CANDLES
  1378	           ============================================ */
  1379	        function blowOutOpeningCandles() {
  1380	            const flames = document.querySelectorAll('#openingOverlay .ponyo-flame');
  1381	            flames.forEach((flame, i) => {
  1382	                setTimeout(() => {
  1383	                    flame.style.animation = 'none';
  1384	                    flame.style.transform = 'translateX(-50%) scale(0)';
  1385	                    flame.style.opacity   = '0';
  1386	                    flame.style.transition = 'all 0.5s ease-out';
  1387	                    const smoke = document.createElement('div');
  1388	                    smoke.style.cssText = `
  1389	                        position: absolute;
  1390	                        width: 10px;
  1391	                        height: 10px;
  1392	                        background: rgba(200, 200, 200, 0.5);
  1393	                        border-radius: 50%;
  1394	                        top: -30px;
  1395	                        left: 50%;
  1396	                        transform: translateX(-50%);
  1397	                        animation: smokeRise 1.5s ease-out forwards;
  1398	                    `;
  1399	                    flame.parentNode.appendChild(smoke);
  1400	                    setTimeout(() => smoke.remove(), 1500);
  1401	                }, i * 200);
  1402	            });
  1403	
  1404	            setTimeout(() => {
  1405	                document.getElementById('openingOverlay').classList.add('hidden');
  1406	                document.getElementById('mainContent').classList.add('visible');
  1407	                startMainScene();
  1408	            }, 1200);
  1409	        }
  1410	
  1411	        let mainCandlesBlown = false;
  1412	
  1413	        function blowMainCandles() {
  1414	            if (mainCandlesBlown) return;
  1415	            mainCandlesBlown = true;
  1416	            const flames = document.querySelectorAll('#mainContent .ponyo-flame');
  1417	            flames.forEach((flame, i) => {
  1418	                setTimeout(() => {
  1419	                    flame.style.animation = 'none';
  1420	                    flame.style.transform = 'translateX(-50%) scale(0)';
  1421	                    flame.style.opacity   = '0';
  1422	                    flame.style.transition = 'all 0.5s ease-out';
  1423	                }, i * 150);
  1424	            });
  1425	            setTimeout(() => {
  1426	                document.getElementById('mainCake').textContent = '🍰';
  1427	                document.querySelector('.name').style.color = '#FFD93D';
  1428	            }, 800);
  1429	        }
  1430	
  1431	        /* ============================================
  1432	           BOUQUET INTERACTION
  1433	           ============================================ */
  1434	        function shakeBouquet() {
  1435	            const bouquet = document.querySelector('.bouquet');
  1436	            bouquet.style.animation = 'none';
  1437	            bouquet.offsetHeight;
  1438	            bouquet.style.animation = 'bouquetSway 0.5s ease-in-out 3';
  1439	            const rect = document.getElementById('bouquet').getBoundingClientRect();
  1440	            for (let i = 0; i < 12; i++) {
  1441	                setTimeout(() => {
  1442	                    createMagicParticle(
  1443	                        rect.left + rect.width / 2,
  1444	                        rect.top  + rect.height / 2
  1445	                    );
  1446	                }, i * 50);
  1447	            }
  1448	        }
  1449	
  1450	        /* ============================================
  1451	           CELEBRATION EFFECTS
  1452	           ============================================ */
  1453	        function createFlowerItem() {
  1454	            const el = document.createElement('div');
  1455	            el.style.cssText = `
  1456	                position: fixed;
  1457	                font-size: ${1.5 + Math.random() * 2}rem;
  1458	                left: ${Math.random() * 95}vw;
  1459	                top: -50px;
  1460	                z-index: 998;
  1461	                pointer-events: none;
  1462	                animation: flowerRain ${2.2 + Math.random() * 2.2}s ease-in forwards;
  1463	            `;
  1464	            el.textContent = flowerEmojis[Math.floor(Math.random() * flowerEmojis.length)];
  1465	            document.body.appendChild(el);
  1466	            setTimeout(() => el.remove(), 5500);
  1467	        }
  1468	
  1469	        function celebrate() {
  1470	            for (let i = 0; i < 35; i++) setTimeout(createFlowerItem, i * 55);
  1471	            for (let i = 0; i < 60; i++) setTimeout(createConfetti, i * 30);
  1472	            for (let i = 0; i < 15; i++) setTimeout(createBubble, i * 100);
  1473	            for (let i = 0; i < 10; i++) setTimeout(createWaterBalloon, i * 200);
  1474	            const name = document.querySelector('.name');
  1475	            name.style.animation = 'none';
  1476	            name.offsetHeight;
  1477	            name.style.animation = 'nameGlow 1s ease-in-out 3';
  1478	        }
  1479	
  1480	        /* ============================================
  1481	           MAIN SCENE
  1482	           ============================================ */
  1483	        function startMainScene() {
  1484	            for (let i = 0; i < 15; i++) createBubble();
  1485	            for (let i = 0; i < 8;  i++) setTimeout(createWaterBalloon, i * 500);
  1486	            for (let i = 0; i < 5;  i++) setTimeout(createFish, i * 2000);
  1487	            for (let i = 0; i < 10; i++) createSparkle();
  1488	            for (let i = 0; i < 6;  i++) createStarfish();
  1489	            intervals.push(setInterval(createBubble, 1500));
  1490	            intervals.push(setInterval(createWaterBalloon, 3000));
  1491	            intervals.push(setInterval(createFish, 8000));
  1492	            intervals.push(setInterval(createSparkle, 800));
  1493	        }
  1494	
  1495	        /* ============================================
  1496	           ENVELOPE OPENING
  1497	           ============================================ */
  1498	        let envelopeOpened = false;
  1499	
  1500	        function openEnvelope() {
  1501	            if (envelopeOpened) return;
  1502	            envelopeOpened = true;
  1503	
  1504	            const bob     = document.getElementById('envelopeBob');
  1505	            const wrapper = document.getElementById('envelopeWrapper');
  1506	
  1507	            const bobY = bob.getBoundingClientRect().top
  1508	                       - bob.parentElement.getBoundingClientRect().top;
  1509	            bob.style.setProperty('--bob-offset', bobY + 'px');
  1510	
  1511	            bob.classList.add('open');
  1512	
  1513	            setTimeout(() => {
  1514	                wrapper.classList.add('open');
  1515	            }, 180);
  1516	
  1517	            setTimeout(() => {
  1518	                document.getElementById('envelopeOverlay').classList.add('hidden');
  1519	            }, 2400);
  1520	        }
  1521	
  1522	        document.getElementById('envelopeOverlay').addEventListener('click', openEnvelope);
  1523	        setTimeout(() => { if (!envelopeOpened) openEnvelope(); }, 5000);
  1524	
  1525	        /* ============================================
  1526	           OPENING OVERLAY HANDLERS
  1527	           ============================================ */
  1528	        document.getElementById('openingOverlay').addEventListener('click', blowOutOpeningCandles);
  1529	        document.getElementById('openingBubble').addEventListener('click', (e) => {
  1530	            e.stopPropagation();
  1531	            blowOutOpeningCandles();
  1532	        });
  1533	
  1534	        /* ============================================
  1535	           EASTER EGG
  1536	           ============================================ */
  1537	        document.getElementById('easterEgg').addEventListener('click', function (e) {
  1538	            e.stopPropagation();
  1539	            const toast = document.getElementById('secretToast');
  1540	            toast.classList.add('show');
  1541	            setTimeout(() => toast.classList.remove('show'), 3800);
  1542	
  1543	            const burst = ['🍖', '🐟', '🍖', '🐡', '🍖', '🌊', '🍖', '🐠'];
  1544	            burst.forEach((emoji, i) => {
  1545	                setTimeout(() => {
  1546	                    const el = document.createElement('div');
  1547	                    el.className = 'flying-item';
  1548	                    el.textContent = emoji;
  1549	                    el.style.fontSize = (1.4 + Math.random() * 0.8) + 'rem';
  1550	                    el.style.right  = (10 + Math.random() * 20) + 'px';
  1551	                    el.style.bottom = '30px';
  1552	                    const angle = (Math.random() * 120 + 120) * (Math.PI / 180);
  1553	                    const dist1 = 100 + Math.random() * 150;
  1554	                    const dist2 = 200 + Math.random() * 250;
  1555	                    el.style.setProperty('--fx',  (-Math.cos(angle) * dist1) + 'px');
  1556	                    el.style.setProperty('--fy',  (-Math.sin(angle) * dist1) + 'px');
  1557	                    el.style.setProperty('--fx2', (-Math.cos(angle) * dist2 + (Math.random() * 60 - 30)) + 'px');
  1558	                    el.style.setProperty('--fy2', (-Math.sin(angle) * dist2 + (Math.random() * 60 - 30)) + 'px');
  1559	                    document.body.appendChild(el);
  1560	                    setTimeout(() => el.remove(), 2900);
  1561	                }, i * 110);
  1562	            });
  1563	        });
  1564	    </script>
  1565	</body>
  1566	</html>
  1567
