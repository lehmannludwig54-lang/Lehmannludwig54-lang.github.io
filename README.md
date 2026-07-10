# Lehmannludwig54-lang.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouthJobX – Next-Gen Teen Job Platform</title>
    <style>
        :root {
            --primary: #4f46e5;
            --primary-hover: #4338ca;
            --secondary: #10b981;
            --danger: #ef4444;
            --warning: #f59e0b;
            --dark: #1f2937;
            --light: #f3f4f6;
            --border: #e5e7eb;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: #f9fafb;
            color: var(--dark);
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* Sidebar Navigation */
        aside {
            width: 260px;
            background-color: white;
            border-right: 1px solid var(--border);
            display: flex;
            flex-direction: column;
            padding: 20px;
        }

        .logo {
            font-size: 22px;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .nav-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
            flex-grow: 1;
        }

        .nav-btn {
            padding: 12px 16px;
            border: none;
            background: none;
            border-radius: 8px;
            text-align: left;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            color: #4b5563;
            transition: 0.2s;
        }

        .nav-btn.active, .nav-btn:hover {
            background-color: var(--light);
            color: var(--primary);
        }

        /* Main Content Windows */
        main {
            flex-grow: 1;
            padding: 40px;
            overflow-y: auto;
            position: relative;
        }

        .view-section {
            display: none;
        }

        .view-section.active {
            display: block;
        }

        h1 { font-size: 28px; margin-bottom: 10px; color: var(--dark); }
        p.subtitle { color: #6b7280; margin-bottom: 30px; }

        /* Component Cards & Boxes */
        .card {
            background: white;
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 24px;
            margin-bottom: 24px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .alert-box {
            background-color: #fffbeb;
            border: 1px solid #fde68a;
            color: #b45309;
            border-radius: 8px;
            padding: 16px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 500;
        }

        /* Forms & Interactive Items */
        label { display: block; font-weight: 600; margin-bottom: 8px; font-size: 14px; }
        input, select, textarea {
            width: 100%; padding: 12px; border: 1px solid var(--border);
            border-radius: 8px; margin-bottom: 20px; font-size: 14px; background: white;
        }
        
        button.btn {
            background-color: var(--primary); color: white; border: none;
            padding: 12px 24px; border-radius: 8px; font-weight: bold; cursor: pointer; transition: 0.2s;
        }
        button.btn:hover { background-color: var(--primary-hover); }
        button.btn-success { background-color: var(--secondary); }

        /* Chat System Grid Layout */
        .chat-container {
            display: grid;
            grid-template-columns: 1fr 320px;
            height: 500px;
            border: 1px solid var(--border);
            border-radius: 12px;
            background: white;
            overflow: hidden;
        }

        .chat-messages {
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 12px;
            background: #f9fafb;
        }

        .msg { max-width: 70%; padding: 12px 16px; border-radius: 12px; font-size: 14px; line-height: 1.4; }
        .msg.incoming { background: white; border: 1px solid var(--border); align-self: flex-start; }
        .msg.outgoing { background: var(--primary); color: white; align-self: flex-end; }
        .msg.contract { background: #ecfdf5; border: 1px solid #a7f3d0; color: #065f46; align-self: flex-start; }

        .chat-sidebar {
            border-left: 1px solid var(--border);
            padding: 20px;
            background: white;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        /* Badges */
        .badge {
            display: inline-block; padding: 4px 10px; border-radius: 12px;
            font-size: 12px; font-weight: bold; background: var(--light); color: var(--dark);
        }
        .badge.ai { background-color: #e0e7ff; color: var(--primary); }
    </style>
</head>
<body>

    <aside>
        <div class="logo">YouthJobX 🚀</div>
        <div class="nav-group">
            <button class="nav-btn active" onclick="switchView('assessment')">1. AI Assessment Quiz</button>
            <button class="nav-btn" onclick="switchView('profile')">2. Mandatory Profile Setup</button>
            <button class="nav-btn" onclick="switchView('dashboard')">3. Teen Employee Dashboard</button>
            <button class="nav-btn" onclick="switchView('employer')">4. Employer DM & Contract Area</button>
        </div>
    </aside>

    <main>

        <section id="assessment" class="view-section active">
            <h1>Initial AI Career Assessment</h1>
            <p class="subtitle">Complete this mandatory query session so our AI model can evaluate your strategic skills and place you in the right working industry.</p>
            
            <div class="card" id="quiz-card">
                <form id="assessmentForm" onsubmit="runAIAssessment(event)">
                    <label>Question 1: If a customer complains that an automated delivery was wrong, how do you respond?</label>
                    <textarea required placeholder="Write your task response here..."></textarea>

                    <label>Question 2: What area of daily work tasks interests you the most?</label>
                    <select id="pref-sector">
                        <option value="Tech Support & Digital">Tech Assistance & Coding Support</option>
                        <option value="Creative & Marketing">Social Media & Creative Assets</option>
                        <option value="Local Commerce & Logistics">Organization, Warehousing & Local Help</option>
                    </select>

                    <button type="submit" class="btn">Process with AI Engine</button>
                </form>
            </div>

            <div class="card" id="quiz-result" style="display:none;">
                <h3 style="color: var(--secondary); margin-bottom: 10px;">✔ Evaluation Complete</h3>
                <p>Based on your task execution matrices, the AI has flagged you for the following sector:</p>
                <div style="margin: 15px 0;"><span class="badge ai" id="assigned-badge" style="font-size: 16px; padding: 8px 16px;">Processing...</span></div>
                <button class="btn" onclick="switchView('profile')">Proceed to Profile Verification</button>
            </div>
        </section>

        <section id="profile" class="view-section">
            <h1>Mandatory Upload Profiles</h1>
            <p class="subtitle">Teen users must maintain verified documentation at all times. Failure to upload will auto-lock your profile validation statuses every 30 days.</p>
            
            <div class="card">
                <form onsubmit="saveProfileData(event)">
                    <label>Applicant Legal Full Name</label>
                    <input type="text" id="p-name" value="Alex Mercer" required>

                    <label>Current Residential Address</label>
                    <input type="text" id="p-address" value="42 Innovation Way, Metro City" required>

                    <label>Verified Age</label>
                    <input type="number" id="p-age" value="16" min="13" max="18" required>

                    <label>Mandatory 1-Minute Application Video Link (YouTube, Vimeo, etc.)</label>
                    <input type="url" id="p-video" placeholder="https://www.youtube.com/watch?v=..." required>

                    <label>Academic Certificates Link (Cloud Storage File)</label>
                    <input type="url" id="p-cert" placeholder="https://drive.google.com/file/..." required>

                    <button type="submit" class="btn">Update Upload Vectors</button>
                </form>
            </div>
        </section>

        <section id="dashboard" class="view-section">
            <h1>Teen Dashboard Hub</h1>
            <p class="subtitle">Overview of your verification timelines and matching industrial listings.</p>

            <div class="alert-box">
                <div>
                    <strong>⏳ Profile Verification Lifespan:</strong> You have <span id="days-left">30</span> days left to renew your video/certificates before system visibility drops to hidden.
                </div>
                <button class="btn btn-success" style="padding: 6px 12px; font-size: 12px;" onclick="switchView('profile')">Renew Now</button>
            </div>

            <div class="card">
                <h3>Your Core Parameters Matrix</h3>
                <div style="margin-top: 15px; display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px;">
                    <div><strong>AI Domain:</strong> <span id="dash-ai" class="badge ai">Run Quiz First</span></div>
                    <div><strong>Video Data Link:</strong> <span id="dash-video" style="color:var(--danger)">Missing Data</span></div>
                    <div><strong>Certificates Link:</strong> <span id="dash-cert" style="color:var(--danger)">Missing Data</span></div>
                </div>
            </div>
        </section>

        <section id="employer" class="view-section">
            <h1>Direct Message Command Center</h1>
            <p class="subtitle">Secure workspace environment where companies communicate and process locked legal payloads.</p>

            <div class="chat-container">
                <div class="chat-messages" id="chatBox">
                    <div class="msg incoming">Hello Alex! We checked out your AI evaluation score and watched your application video. We want to bring you onto our team for the next phase.</div>
                    <div class="msg outgoing">Awesome! I'm ready to work. What are the next steps?</div>
                </div>

                <div class="chat-sidebar">
                    <h3>Action Panel</h3>
                    <p style="font-size: 13px; color: #4b5563;">As an employer, you can execute an automated contract. The system locks down wages to ensure non-negotiable compliant terms.</p>
                    
                    <hr style="border: 0; border-top: 1px solid var(--border);">
                    
                    <div>
                        <label style="margin-bottom: 2px;">Fixed Hourly Compensation</label>
                        <div style="font-size: 18px; font-weight: bold; color: var(--dark); background: var(--light); padding: 10px; border-radius: 6px;">
                            $15.50 / hr <span class="badge" style="vertical-align: middle; margin-left:5px;">Locked</span>
                        </div>
                    </div>

                    <button class="btn" style="width: 100%; margin-top: auto;" onclick="generateAIContract()">⚡ Send AI Contract</button>
                </div>
            </div>
        </section>

    </main>

    <script>
        // Global State Simulation
        let userProfile = {
            name: "Alex Mercer",
            address: "42 Innovation Way, Metro City",
            age: "16",
            aiSector: null,
            videoUrl: null,
            certUrl: null,
            daysRemaining: 30
        };

        // Navigation Engine
        function switchView(viewId) {
            document.querySelectorAll('.view-section').forEach(section => section.classList.remove('active'));
            document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
            
            document.getElementById(viewId).classList.add('active');
            event.target.classList.add('active');
            
            updateDashboardDOM();
        }

        // Section 1 Logic: AI Parser Simulator
        function runAIAssessment(event) {
            event.preventDefault();
            const sectorElement = document.getElementById('pref-sector');
            userProfile.aiSector = sectorElement.options[sectorElement.selectedIndex].text;
            
            document.getElementById('quiz-card').style.display = 'none';
            document.getElementById('quiz-result').style.display = 'block';
            document.getElementById('assigned-badge').innerText = userProfile.aiSector;
        }

        // Section 2 Logic: Storage Simulator
        function saveProfileData(event) {
            event.preventDefault();
            userProfile.name = document.getElementById('p-name').value;
            userProfile.address = document.getElementById('p-address').value;
            userProfile.age = document.getElementById('p-age').value;
            userProfile.videoUrl = document.getElementById('p-video').value;
            userProfile.certUrl = document.getElementById('p-cert').value;
            
            // Simulating update reset of the monthly requirement rule
            userProfile.daysRemaining = 30; 
            
            alert("Verification Payload Saved. Data clock reset to 30 days.");
            switchView('dashboard');
        }

        // Section 3 Logic: DOM Syncer
        function updateDashboardDOM() {
            document.getElementById('days-left').innerText = userProfile.daysRemaining;
            document.getElementById('dash-ai').innerText = userProfile.aiSector ? userProfile.aiSector : "Pending Quiz";
            
            const vSpan = document.getElementById('dash-video');
            if(userProfile.videoUrl) { vSpan.innerText = "Active Link Verified"; vSpan.style.color = "var(--secondary)"; }
            
            const cSpan = document.getElementById('dash-cert');
            if(userProfile.certUrl) { cSpan.innerText = "Active Document Linked"; cSpan.style.color = "var(--secondary)"; }
        }

        // Section 4 Logic: Automated AI Contract Generator Engine
        function generateAIContract() {
            const chatBox = document.getElementById('chatBox');
            
            // Simulation of AI executing content blocks asynchronously
            const systemMessage = document.createElement('div');
            systemMessage.className = 'msg contract';
            systemMessage.innerHTML = `
                <strong>📜 AUTOMATED LABOR CONTRACT GENERATED (AI)</strong><br>
                <small>Auto-Filled Teen Registry Entities:</small><br>
                • <strong>Employee:</strong> ${userProfile.name}<br>
                • <strong>Age Group:</strong> ${userProfile.age} Years Old<br>
                • <strong>Registered Domicile:</strong> ${userProfile.address}<br>
                <hr style="margin: 8px 0; border:0; border-top:1px solid #a7f3d0;">
                • <strong>Wage Rate:</strong> $15.50/hr <span style="font-size:11px; font-weight:normal;">(System Enforced / Non-Negotiable)</span><br><br>
                <button class="btn btn-success" style="padding: 6px 12px; font-size:12px; width:100%; border:0; border-radius:4px; font-weight:bold; cursor:pointer;" onclick="alert('Contract digitally signed!')">Execute Digital Signature</button>
            `;
            
            chatBox.appendChild(systemMessage);
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        // Simple Background Simulator Loop
        setInterval(() => {
            if(userProfile.daysRemaining > 1) {
                userProfile.daysRemaining--;
                document.getElementById('days-left').innerText = userProfile.daysRemaining;
            }
        }, 15000); // Speeds down timeline for demonstration purposes
    </script>
</body>
</html>
