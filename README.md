<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Career Guidance</title>
    <link rel="stylesheet" href="style.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background-color: #f8f9fa;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        select, button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .content-box {
            margin-top: 20px;
            padding: 10px;
            background: #e9ecef;
            display: none;
            border-radius: 5px;
            text-align: left;
        }
        h3 {
            color: #007bff;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Welcome to Student Career Guidance</h1>
        <p>Find the best roadmap and skills for your career path.</p>
        
        <label for="domain">Select Your Interest:</label>
        <select id="domain">
            <option value="AI/ML">AI/ML</option>
            <option value="Web Development">Web Development</option>
            <option value="IoT">IoT</option>
        </select>
        <button onclick="showSuggestions()">Get Roadmap & Skills</button>
        <div id="suggestions" class="content-box"></div>

        <h2>Interview Preparation</h2>
        <button onclick="showInterviewQuestions()">Get Technical Interview Questions</button>
        <div id="interview-questions" class="content-box"></div>

        <h2>HR Interview Preparation</h2>
        <button onclick="showHRQuestions()">Get HR Questions & Tips</button>
        <div id="hr-questions" class="content-box"></div>

        <h2>Career Resources</h2>
        <button onclick="showCareerResources()">Get Career Resources</button>
        <div id="career-resources" class="content-box"></div>

        <h2>Project Ideas</h2>
        <button onclick="showProjectIdeas()">Get Project Ideas</button>
        <div id="project-ideas" class="content-box"></div>
    </div>
    
    <script>
        function showSuggestions() {
            var domain = document.getElementById("domain").value;
            var suggestions = {
                "AI/ML": "Learn Python, Machine Learning, Deep Learning, TensorFlow, and work on projects like Chatbots and Image Recognition.",
                "Web Development": "Start with HTML, CSS, JavaScript, then learn React.js or Angular, and explore backend technologies like Node.js.",
                "IoT": "Understand Arduino, Raspberry Pi, Sensors, Embedded Systems, and work on Smart Home or Healthcare IoT projects."
            };
            document.getElementById("suggestions").innerHTML = `<h3>Recommended Path:</h3><p>${suggestions[domain]}</p>`;
            document.getElementById("suggestions").style.display = "block";
        }
        
        function showInterviewQuestions() {
            var domain = document.getElementById("domain").value;
            var questions = {
                "AI/ML": ["What is the difference between supervised and unsupervised learning?", "Explain overfitting and how to prevent it.", "What are the advantages of using deep learning over traditional machine learning algorithms?"],
                "Web Development": ["What is the difference between HTML and HTML5?", "How does CSS Flexbox work?", "Explain the difference between React.js and Angular."],
                "IoT": ["What are the key components of an IoT system?", "Explain MQTT and its role in IoT communication.", "What are the security challenges in IoT devices?"]
            };
            document.getElementById("interview-questions").innerHTML = formatList("Common Interview Questions", questions[domain]);
            document.getElementById("interview-questions").style.display = "block";
        }
        
        function showHRQuestions() {
            var hrQuestions = [
                "Tell me about yourself.",
                "What are your strengths and weaknesses?",
                "Why do you want to work for this company?",
                "Where do you see yourself in five years?",
                "Describe a challenging situation and how you handled it."
            ];
            document.getElementById("hr-questions").innerHTML = formatList("HR Interview Questions", hrQuestions);
            document.getElementById("hr-questions").style.display = "block";
        }
        
        function showCareerResources() {
            var careerResources = [
                `<a href="https://www.coursera.org" target="_blank">Coursera</a> - Online courses on AI/ML, Web Development, IoT, and more.`,
                `<a href="https://www.udemy.com" target="_blank">Udemy</a> - Affordable tech courses on different domains.`,
                `<a href="https://www.linkedin.com" target="_blank">LinkedIn</a> - Build your professional network and find job opportunities.`,
                `<a href="https://github.com" target="_blank">GitHub</a> - Showcase your projects and collaborate with developers.`,
                `<a href="https://internshala.com" target="_blank">Internshala</a> - Find internships in tech and other fields.`
            ];
            document.getElementById("career-resources").innerHTML = formatList("Useful Career Resources", careerResources, true);
            document.getElementById("career-resources").style.display = "block";
        }
        
        function showProjectIdeas() {
            var domain = document.getElementById("domain").value;
            var projects = {
                "AI/ML": ["Chatbot using NLP", "Fake News Detection", "Handwritten Digit Recognition"],
                "Web Development": ["Portfolio Website", "E-commerce Website", "Blogging Platform"],
                "IoT": ["Smart Home Automation", "Weather Monitoring System", "IoT-based Health Monitoring"]
            };
            document.getElementById("project-ideas").innerHTML = formatList("Recommended Projects", projects[domain]);
            document.getElementById("project-ideas").style.display = "block";
        }

        function formatList(title, items, isHTML = false) {
            let listItems = items.map(item => `<li>${isHTML ? item : escapeHTML(item)}</li>`).join("");
            return `<h3>${title}:</h3><ul>${listItems}</ul>`;
        }

        function escapeHTML(str) {
            return str.replace(/</g, "&lt;").replace(/>/g, "&gt;");
        }
    </script>
</body>
</html>

