
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dalinar | Stone Keeper Dashboard</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700;900&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
    <style>
        :root {
            --stone-dark: #1a1a1a;
            --stone-med: #444444;
            --stone-light: #d6d6d6;
            --leather: #5d4037;
            --leather-light: #8d6e63;
            --parchment: #f0f0f0;
            --ink: #111;
            --blood: #4a0404;
            --heal: #03a062;
            --gold: #d4af37;
            --magic-purple: #5e35b1;
        }
        /* Sidebar Layout */
.sidebar {
    position: fixed;
    right: 20px;
    top: 20px;
    width: 240px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    z-index: 1000;
}

@media (max-width: 1400px) {
    .sidebar { position: static; width: 100%; margin-top: 20px; flex-direction: row; }
}

/* Notes Box */
.notes-area {
    width: 100%;
    height: 150px;
    background: var(--parchment);
    border: 1px solid var(--leather);
    font-family: 'Cormorant Garamond', serif;
    padding: 10px;
    resize: vertical;
    box-sizing: border-box;
    background-image: repeating-linear-gradient(transparent, transparent 23px, rgba(141, 110, 99, 0.2) 24px);
    line-height: 24px;
}

<div class="section">
    <label class="archaic-label">Sacred Vows & Boons</label>
    <div class="passive-box">
        <ul class="passive-list">
            <li>
                <span class="trait-name">Divine Sense</span>
                <span class="trait-desc">Detect celestial, fiend, undead (60ft)</span>
            </li>
            <li>
                <span class="trait-name">Divine Health</span>
                <span class="trait-desc">Immune to all disease</span>
            </li>
            <li>
                <span class="trait-name">Channel Divinity</span>
                <span class="trait-desc">Guided Strike / Conquering Presence</span>
            </li>
            <li>
                <span class="trait-name">Extra Attack</span>
                <span class="trait-desc">Attack twice per action</span>
            </li>
            <li>
                <span class="trait-name">Aura of Protection</span>
                <span class="trait-desc">Add CHA to saves (10ft)</span>
            </li>
            <li>
                <span class="trait-name">Aura of Conquest</span>
                <span class="trait-desc">Frightened creature speed = 0</span>
            </li>
        </ul>
    </div>
</div>

/* Archaic Calculator */
.calc-container {
    background: var(--stone-dark);
    padding: 15px;
    border: 3px double var(--gold);
    border-radius: 5px;
}

#calc-display {
    width: 100%;
    height: 40px;
    background: #2a2a2a;
    color: var(--gold);
    text-align: right;
    padding: 5px;
    font-family: 'Cinzel', serif;
    font-size: 1.2rem;
    border: 1px inset var(--stone-med);
    margin-bottom: 10px;
    box-sizing: border-box;
}

.calc-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 5px;
}

.calc-btn {
    background: var(--stone-med);
    color: var(--stone-light);
    border: 1px solid var(--leather);
    font-family: 'Cinzel', serif;
    padding: 10px 5px;
    cursor: pointer;
    transition: 0.2s;
}

.calc-btn:hover { background: var(--leather); color: white; }
.calc-btn.op { color: var(--gold); font-weight: bold; }

        body {
            font-family: 'Cormorant Garamond', serif;
            background-color: var(--stone-light);
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%239C92AC' fill-opacity='0.1' fill-rule='evenodd'/%3E%3C/svg%3E");
            color: var(--ink); margin: 0; padding: 20px; min-height: 100vh;
        }

        h1, h2, h3, h4 { font-family: 'Cinzel', serif; text-transform: uppercase; letter-spacing: 0.1em; color: var(--stone-dark); }
        header { border-bottom: 4px double var(--stone-dark); padding-bottom: 20px; margin-bottom: 30px; text-align: center; }
        h1 { font-size: 3rem; margin: 0; font-weight: 900; }
        .tracker-card h4 { color: var(--gold); }
        .subtitle { font-size: 1.2rem; color: var(--leather); font-weight: bold; }

        .tabs { display: flex; justify-content: center; gap: 10px; margin-bottom: 25px; }
        .tab-btn {
            background: var(--stone-dark); color: var(--stone-light); border: 2px solid var(--leather);
            padding: 12px 30px; cursor: pointer; font-family: 'Cinzel', serif; font-weight: bold;
            box-shadow: 2px 2px 0px var(--leather-light);
        }
        .tab-btn.active { background: var(--leather); color: white; transform: translateY(1px); box-shadow: none; }

        .tab-content { display: none; animation: fadeEffect 0.4s; }
        .tab-content.active { display: block; }

        /* Trackers */
        .tracker-container { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin-bottom: 20px; }
        .tracker-card { background: var(--stone-dark); color: var(--parchment); padding: 15px; border: 2px solid var(--leather); text-align: center; }
        .current-value { font-size: 2.5rem; font-family: 'Cinzel', serif; font-weight: 900; line-height: 1; }
        
        /* Stats Table */
        .stats-row { display: grid; grid-template-columns: repeat(6, 1fr); background: var(--stone-dark); color: white; border: 2px solid var(--leather); margin-bottom: 20px; }
        .stat-box { padding: 10px; text-align: center; border-right: 1px solid var(--leather); }
        .skill-list { font-size: 0.75rem; text-align: left; list-style: none; padding: 5px; margin-top: 5px; border-top: 1px solid #444; color: #ccc; }
        .prof-dot { color: var(--heal); margin-right: 3px; }
        .exp-star { color: var(--gold); margin-right: 3px; }

        /* Layout Grid */
        .main-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        @media (max-width: 900px) { .main-grid { grid-template-columns: 1fr; } }

        /* Card Styles */
        .card { background: var(--parchment); border: 3px double var(--stone-dark); padding: 20px; margin-bottom: 20px; box-shadow: 5px 5px 15px rgba(0,0,0,0.1); }
        .card h3 { border-bottom: 2px solid var(--stone-dark); margin-top: 0; padding-bottom: 5px; }

        /* Weapon Toggle */
        .weapon-box { background: rgba(0,0,0,0.07); padding: 15px; border-radius: 5px; border: 1px solid var(--stone-med); margin-bottom: 15px; }
        .toggle-container { display: flex; align-items: center; justify-content: space-between; margin-top: 10px; font-weight: bold; font-family: 'Cinzel'; }
        .switch { position: relative; display: inline-block; width: 44px; height: 22px; }
        .switch input { opacity: 0; width: 0; height: 0; }
        .slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: #ccc; transition: .4s; border-radius: 22px; }
        .slider:before { position: absolute; content: ""; height: 16px; width: 16px; left: 3px; bottom: 3px; background-color: white; transition: .4s; border-radius: 50%; }
        input:checked + .slider { background-color: var(--magic-purple); }
        input:checked + .slider:before { transform: translateX(22px); }

        /* Diamond Spell Slots */
        .slot-row { display: flex; align-items: center; gap: 15px; margin-bottom: 15px; background: rgba(0,0,0,0.05); padding: 10px; border-radius: 4px; }
        .diamond-group { display: flex; gap: 15px; }
        .diamond-chk { display: none; }
        .diamond-lbl { 
            width: 18px; height: 18px; background: white; border: 2px solid var(--stone-dark); 
            transform: rotate(45deg); cursor: pointer; transition: 0.2s; display: block;
        }
        .diamond-chk:checked + .diamond-lbl { background: var(--stone-dark); box-shadow: 0 0 8px var(--gold); }

        .spell-table { width: 100%; border-collapse: collapse; font-size: 0.85rem; margin-top: 10px; background: white; }
        .spell-table th, .spell-table td { border: 1px solid var(--stone-med); padding: 8px; text-align: left; }
        .spell-table th { background: var(--stone-dark); color: white; text-transform: uppercase; }

        .controls { display: flex; gap: 5px; margin-top: 5px; }
        .controls input { width: 65px; text-align: center; font-weight: bold; }
        .controls button { flex: 1; cursor: pointer; padding: 5px; font-family: 'Cinzel'; font-weight: bold; border: 1px solid var(--stone-dark); }
        
        @keyframes fadeEffect { from {opacity: 0;} to {opacity: 1;} }
        
        /* Passive Box Styling */
    .passive-box {
    background: #fdf6e3;
    border: 1px solid #a1887f;
    padding: 5px;
    }

    .passive-list {
    list-style-type: none; /* Remove default bullets */
    padding: 0;
    margin: 0;
    }

    .passive-list li {
    padding: 6px;
    border-bottom: 1px dashed #a1887f; /* Dashed line between traits */
    }

    .passive-list li:last-child {
    border-bottom: none;
    }

    .trait-name {
    display: block;
    font-weight: bold;
    font-variant: small-caps; /* Looks more like a header */
    color: #3e2723;
    font-size: 1em;
    }

    .trait-desc {
    font-size: 0.85em;
    font-style: italic;
    color: #5d4037;
    }
    </style>
</head>
<body>

<header>
    <h1>Dalinar Gottfaust</h1>
    <div class="subtitle">Level 8 Conquest Paladin • Kalashtar</div>
</header>

<div class="tabs">
    <button class="tab-btn active" onclick="openTab('guardian')">The Guardian</button>
    <button class="tab-btn" onclick="openTab('library')">The Library</button>
</div>

<div id="guardian" class="tab-content active">
    <div class="tracker-container">
        <div class="tracker-card">
            <h4>HIT POINTS</h4>
            <div class="current-value" id="currentHP" style="color:var(--heal)">76</div>
            <div class="controls"><input type="number" id="hpIn" value="10"><button style="background:var(--blood); color:white" onclick="adj('HP',-1)">Dmg</button><button style="background:var(--heal)" onclick="adj('HP',1)">Heal</button></div>
        </div>
        <div class="tracker-card">
            <h4>LAY ON HANDS</h4>
            <div class="current-value" id="currentLOH" style="color:var(--leather-light)">40</div>
            <div class="controls"><input type="number" id="lohIn" value="5"><button style="background:var(--leather); color:white" onclick="adj('LOH',-1)">Use</button></div>
        </div>
        <div class="tracker-card">
            <h4>GOLD</h4>
            <div class="current-value" id="currentGP" style="color:var(--gold)">60</div>
            <div class="controls"><input type="number" id="gpIn" value="10"><button style="background:var(--leather); color:white" onclick="adj('GP',-1)">Pay</button><button style="background:var(--heal)" onclick="adj('GP',1)">Add</button></div>
        </div>
    </div>

    <div class="stats-row">
        <div class="stat-box"><span>STR</span><div style="font-size:1.4rem">20 (+5)</div><ul class="skill-list"><li><span class="exp-star">★</span>Save (+11)</li><li><span class="exp-star">★</span>Athletics (+11)</li></ul></div>
        <div class="stat-box"><span>DEX</span><div style="font-size:1.4rem">14 (+2)</div><ul class="skill-list"><li>Acrobatics (+2)</li><li>Stealth (+2)</li></ul></div>
        <div class="stat-box"><span>CON</span><div style="font-size:1.4rem">18 (+4)</div><ul class="skill-list"><li><span class="prof-dot">●</span>Save (+7)</li></ul></div>
        <div class="stat-box"><span>INT</span><div style="font-size:1.4rem">12 (+1)</div><ul class="skill-list"><li>Religion (+1)</li></ul></div>
        <div class="stat-box"><span>WIS</span><div style="font-size:1.4rem">14 (+2)</div><ul class="skill-list"><li><span class="prof-dot">●</span>Animal H. (+5)</li><li><span class="prof-dot">●</span>Insight (+5)</li><li><span class="prof-dot">●</span>Perception (+5)</li><li><span class="exp-star">★</span>Medicine (+8)</li></ul></div>
        <div class="stat-box"><span>CHA</span><div style="font-size:1.4rem">16 (+3)</div><ul class="skill-list"><li><span class="prof-dot">●</span>Save (+6)</li><li><span class="prof-dot">●</span>Persuasion (+6)</li><li>Intimidate (+3)</li></ul></div>
    </div>

    <div class="main-grid">
        <div class="card">
            <h3>Inventory & Armory</h3>
            <div class="weapon-box">
                <strong>HelmsFist (Maul)</strong><br>
                <em style="font-size:0.9rem">+8 to hit | 1d12 + 5 bludgeoning</em>
                <div class="toggle-container">
                    <span>Primordis (Active: +1d4)</span>
                    <label class="switch"><input type="checkbox" id="primordis"><span class="slider"></span></label>
                </div>
            </div>
            
            <p><strong>Magic Plate Armor:</strong> AC 18. No fall damage &lt; 100ft. Ignores non-magical P/S/B damage if hit is &lt; 12.</p>
            
            <ul style="font-size: 0.9rem; line-height: 1.6;">
                <li><strong>5 Harpoons:</strong> Heavy thrown weapons.</li>
                <li><strong>Sending Stones:</strong> To Lysander and Tellaris.</li>
                <li><strong>Explorer's Pack:</strong> Rations, bedroll, rope, etc.</li>
                <li><strong>Sick Shield:</strong> Reflects projectiles if Attack == AC.</li>
            </ul>
        </div>

        <div class="card">
            <h3>Companions</h3>
            <div class="weapon-box">
                <strong>Polaris (Owlbear Steed)</strong><br>
                HP: <span id="polHP" style="font-weight:bold; color:var(--heal)">60</span> / 60<br>
                Claws: +7 to hit | 2d8+5 damage
                <div class="controls"><input type="number" id="polIn" value="5"><button style="background:var(--blood); color:white" onclick="adj('POL',-1)">Dmg</button><button style="background:var(--heal)" onclick="adj('POL',1)">Heal</button></div>
            </div>
            <p><strong>Bron Bedrock:</strong> Master Blacksmith.</p>
            <p><strong>Ember Bedrock:</strong> Bron's daughter (Age 7).</p>
        </div>
    </div>
</div>

<div id="library" class="tab-content">
    <div class="card">
        <h3>Spell Slot Tracker</h3>
        <div class="slot-row">
            <strong style="width:100px;">1st Level (4)</strong>
            <div class="diamond-group">
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
            </div>
        </div>
        <div class="slot-row">
            <strong style="width:100px;">2nd Level (3)</strong>
            <div class="diamond-group">
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
                <label><input type="checkbox" class="diamond-chk"><span class="diamond-lbl"></span></label>
            </div>
        </div>
        <p style="text-align:center; font-weight:bold; margin:0;">Save DC: 14 | Attack: +6</p>
    </div>

    <div class="card">
        <h3>Specialized Magic (Feats & Oath)</h3>
        <table class="spell-table">
            <tr><th>Spell</th><th>Type</th><th>Brief Effect</th></tr>
            <tr><td>Armor of Agathys</td><td style="color:var(--leather)">Oath</td><td>+5 Temp HP; attackers take 5 cold dmg.</td></tr>
            <tr><td>Command</td><td style="color:var(--leather)">Oath</td><td>Target obeys a one-word command.</td></tr>
            <tr><td>Hold Person</td><td style="color:var(--leather)">Oath</td><td>Paralyze one humanoid (Wis Save).</td></tr>
            <tr><td>Spiritual Weapon</td><td style="color:var(--leather)">Oath</td><td>Spectral weapon bonus action attacks.</td></tr>
            <tr><td>Silvery Barbs</td><td style="color:var(--magic-purple)">Feat</td><td>React to force reroll; give ally advantage.</td></tr>
            <tr><td>Misty Step</td><td style="color:var(--magic-purple)">Feat</td><td>Bonus action teleport 30ft.</td></tr>
        </table>

        <h3 style="margin-top:20px;">Paladin Library</h3>
        <table class="spell-table">
            <thead><tr><th>Lvl</th><th>Spell</th><th>Brief Description</th></tr></thead>
            <tbody>
                <tr><td>1</td><td>Bless</td><td>3 allies add 1d4 to attacks and saves.</td></tr>
                <tr><td>1</td><td>Command</td><td>Target obeys a one-word command (Wis Save).</td></tr>
                <tr><td>1</td><td>Cure Wounds</td><td>Heal touched creature 1d8 + Charisma mod.</td></tr>
                <tr><td>1</td><td>Detect Evil/Good</td><td>Sense presence of celestials, fiends, undead, etc.</td></tr>
                <tr><td>1</td><td>Detect Magic</td><td>Sense magic presence and school within 30ft.</td></tr>
                <tr><td>1</td><td>Detect Poison/Dis</td><td>Sense presence/type of poison or disease.</td></tr>
                <tr><td>1</td><td>Divine Favor</td><td>Your weapon attacks deal extra 1d4 radiant dmg.</td></tr>
                <tr><td>1</td><td>Heroism</td><td>Target immune to fear; gain Temp HP each turn.</td></tr>
                <tr><td>1</td><td>Prot. from Evil/G</td><td>Creature types have disadv. vs target.</td></tr>
                <tr><td>1</td><td>Purify Food/Drink</td><td>Nonmagical food/drink is decontaminated.</td></tr>
                <tr><td>1</td><td>Shield of Faith</td><td>+2 AC to one creature for 10 min.</td></tr>
                <tr><td>2</td><td>Aid</td><td>+5 Max/Current HP for 3 allies (8 hrs).</td></tr>
                <tr><td>2</td><td>Branding Smite</td><td>Hit deals +2d6 radiant; target glows.</td></tr>
                <tr><td>2</td><td>Find Steed</td><td>Summon Polaris (Spirit Owlbear).</td></tr>
                <tr><td>2</td><td>Lesser Restoration</td><td>Cure Blind, Deaf, Paralyzed, or Poisoned.</td></tr>
                <tr><td>2</td><td>Locate Object</td><td>Sense direction of object within 1000ft.</td></tr>
                <tr><td>2</td><td>Magic Weapon</td><td>Touch a non-magical weapon to make it +1.</td></tr>
                <tr><td>2</td><td>Prot. from Poison</td><td>Resistance and advantage vs poison for 1 hr.</td></tr>
                <tr><td>2</td><td>Zone of Truth</td><td>Creatures in 15ft radius cannot lie.</td></tr>
            </tbody>
        </table>
    </div>
    
</div>
</div>

</table>
    </div>
</div> <div class="sidebar">
    <div class="card" style="margin-bottom:0; padding:15px;">
        <h4 style="margin-top:0; font-size:0.9rem;">Chronicle Notes</h4>
        <textarea class="notes-area" placeholder="Record your deeds..."></textarea>
    </div>

    <div class="calc-container">
        <h4 style="color:var(--gold); margin-top:0; font-size:0.8rem; text-align:center;">Abacus of Gottfaust</h4>
        <input type="text" id="calc-display" readonly value="0">
        <div class="calc-grid">
            <button class="calc-btn" onclick="cClear()">C</button>
            <button class="calc-btn op" onclick="cIn('/')">/</button>
            <button class="calc-btn op" onclick="cIn('*')">×</button>
            <button class="calc-btn op" onclick="cDel()">←</button>
            
            <button class="calc-btn" onclick="cIn('7')">7</button>
            <button class="calc-btn" onclick="cIn('8')">8</button>
            <button class="calc-btn" onclick="cIn('9')">9</button>
            <button class="calc-btn op" onclick="cIn('-')">-</button>
            
            <button class="calc-btn" onclick="cIn('4')">4</button>
            <button class="calc-btn" onclick="cIn('5')">5</button>
            <button class="calc-btn" onclick="cIn('6')">6</button>
            <button class="calc-btn op" onclick="cIn('+')">+</button>
            
            <button class="calc-btn" onclick="cIn('1')">1</button>
            <button class="calc-btn" onclick="cIn('2')">2</button>
            <button class="calc-btn" onclick="cIn('3')">3</button>
            <button class="calc-btn op" style="grid-row: span 2; background:var(--gold); color:var(--stone-dark)" onclick="cSolve()">=</button>
            
            <button class="calc-btn" style="grid-column: span 2;" onclick="cIn('0')">0</button>
            <button class="calc-btn" onclick="cIn('.')">.</button>
        </div>
    </div>   
</div>

<script>
    const S = {
        'HP': { id: 'currentHP', in: 'hpIn', max: 76 },
        'LOH': { id: 'currentLOH', in: 'lohIn', max: 40 },
        'GP': { id: 'currentGP', in: 'gpIn', max: 99999 },
        'POL': { id: 'polHP', in: 'polIn', max: 60 }
    };

    function adj(k, m) {
        const d = document.getElementById(S[k].id);
        const val = parseInt(document.getElementById(S[k].in).value);
        let current = parseInt(d.textContent) + (val * m);
        d.textContent = Math.max(0, Math.min(S[k].max, current));
    }

    function openTab(name) {
        document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        document.getElementById(name).classList.add('active');
        event.currentTarget.classList.add('active');
    }
    const cDisp = document.getElementById('calc-display');

function cIn(v) {
    if (cDisp.value === "0" || cDisp.value === "Error") cDisp.value = v;
    else cDisp.value += v;
}

function cClear() { cDisp.value = "0"; }

function cDel() {
    cDisp.value = cDisp.value.slice(0, -1);
    if (cDisp.value === "") cDisp.value = "0";
}

function cSolve() {
    try {
        // Using Function() instead of eval() for slightly better safety
        cDisp.value = Function('"use strict";return (' + cDisp.value + ')')();
    } catch (e) {
        cDisp.value = "Error";
    }
}
</script>
</body>
</html>
