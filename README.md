<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouthJobX Portal</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <aside>
        <div class="logo">YouthJobX //</div>
        <div class="nav-group">
            <button class="nav-btn active" onclick="switchView('registration')">01 / Account Type</button>
            <button class="nav-btn" onclick="switchView('assessment')">02 / AI Competency Quiz</button>
            <button class="nav-btn" onclick="switchView('profile')">03 / Profile Integration</button>
            <button class="nav-btn" onclick="switchView('dashboard')">04 / Employee Dashboard</button>
            <button class="nav-btn" onclick="switchView('employer')">05 / Corporate Workspace</button>
        </div>
    </aside>

    <main>
        <section id="registration" class="view-section active">
            <h1>Select Portal Destination</h1>
            <p class="subtitle">Define your system level role access parameters to populate your workspace environment.</p>
            <div class="role-grid">
                <div class="role-card" onclick="switchView('assessment')">
                    <h3>Teen Employee</h3>
                    <p>Ages 13-18. Complete tactical quizzes, store verified video data streams, and evaluate job contracts.</p>
                </div>
                <div class="role-card" onclick="switchView('employer')">
                    <h3>Private Individual</h3>
                    <p>Post small-scale local yard tasks, property maintenance help, or household assignments with locked wages.</p>
                </div>
                <div class="role-card" onclick="switchView('employer')">
                    <h3>Verified Company</h3>
                    <p>Corporate access pipelines. Browse vetted teen profiles and instantly distribute legal direct contract modules.</p>
                </div>
            </div>
        </section>

        <section id="assessment" class="view-section">
            <h1>Automated AI Skill Placement</h1>
            <p class="subtitle">Complete the problem analysis sequence. Our neural parser routing engine will categorize your tactical industry match.</p>
            <div class="card" id="quiz-card">
                <form onsubmit="runAIAssessment(event)">
                    <label>Scenario Evaluator: A customer order encounters processing delays. Detail your automated tracking adjustments.</label>
                    <textarea required placeholder="Input tactical text parameters..." rows="4"></textarea>
                    <label>Primary Field of Work Focus Selection</label>
                    <select id="pref-sector">
                        <option value="Logistics & Local Help">Logistics, Property Management & Local Help</option>
                        <option value="Media & Creative Assets">Media, Editing & Digital Creative Assets</option>
                        <option value="Technical Operations">Technical Operations & Computational Support</option>
                    </select>
                    <button type="submit" class="btn-black">Execute Analysis Engine</button>
                </form>
            </div>
            <div class="card" id="quiz-result" style="display:none;">
                <h3 style="margin-bottom: 12px; text-transform: uppercase; font-size: 14px; letter-spacing: 0.5px;">✔ Evaluation Processing Node Successful</h3>
                <p style="font-size: 15px; margin-bottom: 20px;">The AI Engine has indexed your profile parameters to the following structural match category:</p>
                <div style="margin-bottom: 25px;"><span class="mono-tag" id="assigned-badge" style="font-size: 14px; padding: 6px 12px;">Allocating...</span></div>
                <button class="btn-black" onclick="switchView('profile')">Initialize Mandatory Document Setup</button>
            </div>
        </section>

        <section id="profile" class="view-section">
            <h1>Mandatory Authentication Files</h1>
            <p class="subtitle">Employee accounts must maintain active links to validation streams. Profiling vectors refresh automatically every 30 days.</p>
            <div class="card">
                <form onsubmit="saveProfileData(event)">
                    <label>Legal Identification Name</label>
                    <input type="text" id="p-name" value="Alex Mercer" required>
                    <label>Primary Residence Location</label>
                    <input type="text" id="p-address" value="42 Innovation Way, Metro City" required>
                    <label>Age Verification Field (Locked scope 13-18)</label>
                    <input type="number" id="p-age" value="16" min="13" max="18" required>
                    <label>Required 1-Minute Pitch Video Data Link</label>
                    <input type="url" id="p-video" placeholder="https://video-storage.com/stream/..." required>
                    <label>Academic & Verification Documents Folder Link</label>
                    <input type="url" id="p-cert" placeholder="https://secure-drive.com/docs/..." required>
                    <button type="submit" class="btn-black">Commit Asset Matrix</button>
                </form>
            </div>
        </section>

        <section id="dashboard" class="view-section">
            <h1>Employee Core Dashboard</h1>
            <p class="subtitle">System notifications, compliance clocks, and system metrics oversight.</p>
            <div class="alert-countdown">
                <div>
                    <strong>⏳ Data Longevity Alert:</strong> Your profiles require monthly data verification. System hiding processes trigger automatically in <span id="days-left" style="font-weight: 700; text-decoration: underline;">30</span> days.
                </div>
                <button class="btn-outline" style="background: var(--white); color: var(--black); padding: 6px 12px; font-size: 11px; text-transform: uppercase; font-weight: 700;" onclick="switchView('profile')">Update System Now</button>
            </div>
            <div class="card">
                <h3 style="font-size: 14px; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 20px;">Vetted Parameter Verification Status</h3>
                <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px;">
                    <div><label>AI Domain Assignment</label><span id="dash-ai" class="mono-tag">Execute Stage 02</span></div>
                    <div><label>Video Array Link</label><span id="dash-video" style="font-size: 13px; color: var(--grey);">Not Synchronized</span></div>
                    <div><label>Certificates Link</label><span id="dash-cert" style="font-size: 13px; color: var(--grey);">Not Synchronized</span></div>
                </div>
            </div>
        </section>

        <section id="employer" class="view-section">
            <h1>Secure Communication Desk</h1>
            <p class="subtitle">Encrypted workplace channel. Review user media matrices and deploy locked, automated legal contracts.</p>
            <div class="chat-container">
                <div class="chat-messages" id="chatBox">
                    <div class="msg incoming">Hello Alex, we have reviewed your analytical profile and application pitch media. We wish to establish a working pipeline.</div>
                    <div class="msg outgoing">Understood. I am prepared to initialize operations. Please distribute the platform agreements.</div>
                </div>
                <div class="chat-sidebar">
                    <h3 style="font-size: 12px; text-transform: uppercase; letter-spacing: 0.5px;">Operational Engine</h3>
                    <p style="font-size: 12px; color: var(--grey); line-height: 1.4;">Wages are strictly system enforced and fully locked out from external negotiation procedures.</p>
                    <div style="margin-top: 10px;">
                        <label>Compensation Index</label>
                        <div style="font-size: 16px; font-weight: 700; background: var(--light-grey); padding: 12px; border: 1px solid var(--border-grey); border-radius: 4px;">
                            $15.50 / hr <span class="mono-tag" style="float: right; margin-top: 1px;">Enforced</span>
                        </div>
                    </div>
                    <button class="btn-black" style="width: 100%; margin-top: auto; padding: 14px;" onclick="generateAIContract()">⚡ Send AI Contract</button>
                </div>
            </div>
        </section>
    </main>

    <script>
        let userProfile = {
            name: "Alex Mercer",
            address: "42 Innovation Way, Metro City",
            age: "16",
            aiSector: null,
            videoUrl: null,
            certUrl: null,
            daysRemaining: 30
        };

        function switchView(viewId) {
            document.querySelectorAll('.view-section').forEach(section => section.classList.remove('active'));
            document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
            document.getElementById(viewId).classList.add('active');
            
            const buttons = Array.from(document.querySelectorAll('.nav-btn'));
            const matchedBtn = buttons.find(btn => btn.getAttribute('onclick').includes(viewId));
            if(matchedBtn) matchedBtn.classList.add('active');
            
            updateDashboardDOM();
        }

        function runAIAssessment(event) {
            event.preventDefault();
            const sectorSelector = document.getElementById('pref-sector');
            userProfile.aiSector = sectorSelector.options[sectorSelector.selectedIndex].text;
            document.getElementById('quiz-card').style.display = 'none';
            document.getElementById('quiz-result').style.display = 'block';
            document.getElementById('assigned-badge').innerText = userProfile.aiSector;
        }

        function saveProfileData(event) {
            event.preventDefault();
            userProfile.name = document.getElementById('p-name').value;
            userProfile.address = document.getElementById('p-address').value;
            userProfile.age = document.getElementById('p-age').value;
            userProfile.videoUrl = document.getElementById('p-video').value;
            userProfile.certUrl = document.getElementById('p-cert').value;
            userProfile.daysRemaining = 30;
            alert("Verification payload synchronized. Compliance timer tracking reset to 30 days.");
            switchView('dashboard');
        }

        function updateDashboardDOM() {
            document.getElementById('days-left').innerText = userProfile.daysRemaining;
            document.getElementById('dash-ai').innerText = userProfile.aiSector ? userProfile.aiSector : "Awaiting Data";
            
            const videoSpan = document.getElementById('dash-video');
            if(userProfile.videoUrl) { videoSpan.innerText = "Verified Link Active"; videoSpan.style.color = "var(--black)"; videoSpan.style.fontWeight = "bold"; }
            
            const certSpan = document.getElementById('dash-cert');
            if(userProfile.certUrl) { certSpan.innerText = "Verified Storage Active"; certSpan.style.color = "var(--black)"; certSpan.style.fontWeight = "bold"; }
        }

        function generateAIContract() {
            const chatBox = document.getElementById('chatBox');
            const contractMsg = document.createElement('div');
            contractMsg.className = 'msg contract-payload';
            contractMsg.innerHTML = `
                <div style="font-weight: 800; text-transform: uppercase; font-size: 11px; letter-spacing: 0.5px; margin-bottom: 10px;">// SYSTEM AI GENERATED CONTRACT MODULE //</div>
                <div style="font-size: 13px; color: var(--dark-grey); line-height: 1.5; margin-bottom: 15px;">
                    This file registers a work intent binding between the issuing verification firm and employee <strong>${userProfile.name}</strong> (${userProfile.age} Y/O), localized at <strong>${userProfile.address}</strong>.<br><br>
                    Wages are absolute and locked by the system kernel core to: <strong>$15.50/hr</strong>.
                </div>
                <button class="btn-black" style="width: 100%; padding: 8px; font-size: 11px; text-transform: uppercase;" onclick="alert('Contract digitally confirmed.')">Execute Digital Signature Block</button>
            `;
            chatBox.appendChild(contractMsg);
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        setInterval(() => {
            if(userProfile.daysRemaining > 1) {
                userProfile.daysRemaining--;
                const counterNode = document.getElementById('days-left');
                if(counterNode) counterNode.innerText = userProfile.daysRemaining;
            }
        }, 20000);
    </script>
</body>
</html>
