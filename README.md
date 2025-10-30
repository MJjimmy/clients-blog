# clients-blog
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Data — Jack | Data Analyst</title>
  <meta name="description" content="Jack — Data Analyst. Exploring ideas through data and creativity." />
  <link rel="stylesheet" href="style/index.css" />
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <h1 class="site-title">Blog</h1>
        <p class="tagline">Exploring ideas through data and creativity.</p>
      </div>
      <div class="header-title">Jack Data Analyst</div>
    </header>

    <main>
      <section class="hero">
        <div class="portrait">
          <!-- Replace with your portrait: assets/jack-hero.jpg -->
          <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" alt="Jack portrait" />
        </div>

        <div class="hero-card">
          <h2>Hi — I'm Jack, a Data Analyst</h2>
          <p class="lead">I turn messy data into clear answers. I work with SQL, Python, and visualization tools to help teams make data-driven decisions. I enjoy building dashboards, exploring datasets, and telling stories with charts.</p>
          <div class="cta"><a class="btn" href="#contact">Get in touch</a></div>
        </div>
      </section>

      <section class="grid-3">
        <div class="card about">
          <h3>About me</h3>
          <p>I'm Jack  a data analyst who loves digging into data to find patterns that matter. I've worked on data cleaning, ETL pipelines, dashboarding, and exploratory analysis. I value clarity, reproducibility, and elegant code.</p>
        </div>

        <div class="card skills">
          <h3>Skills</h3>
          <ul>
            <li>Python (Pandas, NumPy)</li>
            <li>SQL (Postgres, MySQL)</li>
            <li>Data Visualization (Power BI, Tableau, Matplotlib)</li>
            <li>Machine Learning (scikit-learn)</li>
            <li>Excel &amp; Google Sheets</li>
            <li>ETL &amp; Data Pipelines</li>
          </ul>
        </div>

        <div class="card stats">
          <h3>What I'm good at</h3>
          <p>Turning business questions into measurable metrics, building dashboards, cleaning messy data, and communicating results to non-technical stakeholders.</p>
        </div>
      </section>

      <section class="projects">
        <h3>Selected projects</h3>
        <div class="card project">
          <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80" alt="Sales dashboard thumbnail">
          <div>
            <strong>Sales Dashboard — Retail Analysis</strong>
            <div class="project-description">Interactive Power BI dashboard showing month-over-month revenue, top products, and customer segments.</div>
          </div>
        </div>

        <div class="card project">
          <img src="https://images.unsplash.com/photo-1555949963-aa79dcee981c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80" alt="Churn analysis thumbnail">
          <div>
            <strong>Customer Churn Model</strong>
            <div class="project-description">Logistic regression model to predict churn with feature engineering and model explainability notes.</div>
          </div>
        </div>
      </section>

      <section class="card blog">
        <h3>Blog — Insights &amp; How-tos</h3>
        <p>Short posts about data analysis techniques, tutorials, and quick tips for using SQL, Python, and BI tools. (Add your posts in the /posts folder or link to a CMS.)</p>
      </section>

      <section class="card visitor-log">
        <h3>Visitor Log</h3>
        <p>Track and visualize visitor activity on this portfolio (demo using localStorage).</p>
        
        <div class="log-controls">
          <button class="log-btn active" id="show-all">All Visits</button>
          <button class="log-btn" id="show-today">Today</button>
          <button class="log-btn" id="show-week">This Week</button>
          <button class="log-btn" id="clear-log">Clear Log</button>
        </div>
        
        <div class="log-container" id="log-container">
          <!-- Log entries will be inserted here by JavaScript -->
        </div>
        
        <div style="margin-top: 15px; font-size: 13px; color: var(--muted);">
          Total visits: <span id="total-visits">0</span> | 
          Unique visitors: <span id="unique-visitors">0</span>
        </div>
      </section>

      <section id="contact" class="card contact">
        <h3>Contact</h3>
        <p>Email: <a href="mailto:jack@example.com">jack@example.com</a></p>
        <p>Or use the form below (example, needs a backend to work):</p>
        <form action="#" onsubmit="alert('This is a demo form. Replace with a real endpoint.')">
          <input placeholder="Your name" type="text" required />
          <input placeholder="Email" type="email" required />
          <textarea placeholder="Message" rows="4" required></textarea>
          <button type="submit" class="btn">Send message</button>
        </form>
      </section>
    </main>

    <footer>
      Built with ♥ — Jack | Data • <span>© 2025</span>
    </footer>
  </div>

  <script>
    // Visitor Log functionality
    document.addEventListener('DOMContentLoaded', function() {
      const logContainer = document.getElementById('log-container');
      const totalVisitsElement = document.getElementById('total-visits');
      const uniqueVisitorsElement = document.getElementById('unique-visitors');
      const showAllBtn = document.getElementById('show-all');
      const showTodayBtn = document.getElementById('show-today');
      const showWeekBtn = document.getElementById('show-week');
      const clearLogBtn = document.getElementById('clear-log');
      
      let currentFilter = 'all';
      
      // Initialize visitor log
      function initVisitorLog() {
        // Get existing log or create empty array
        let visitorLog = JSON.parse(localStorage.getItem('visitorLog')) || [];
        let uniqueVisitors = JSON.parse(localStorage.getItem('uniqueVisitors')) || [];
        
        // Check if this is a new visitor
        const visitorId = generateVisitorId();
        const isNewVisitor = !uniqueVisitors.includes(visitorId);
        
        if (isNewVisitor) {
          uniqueVisitors.push(visitorId);
          localStorage.setItem('uniqueVisitors', JSON.stringify(uniqueVisitors));
        }
        
        // Add new visit to log
        const visit = {
          id: visitorId,
          timestamp: new Date().toISOString(),
          isNew: isNewVisitor
        };
        
        visitorLog.unshift(visit);
        localStorage.setItem('visitorLog', JSON.stringify(visitorLog));
        
        // Update display
        updateLogDisplay();
      }
      
      // Generate a simple visitor ID (in a real app, this would be more sophisticated)
      function generateVisitorId() {
        let visitorId = localStorage.getItem('visitorId');
        if (!visitorId) {
          visitorId = 'visitor_' + Math.random().toString(36).substr(2, 9);
          localStorage.setItem('visitorId', visitorId);
        }
        return visitorId;
      }
      
      // Format date for display
      function formatDate(dateString) {
        const date = new Date(dateString);
        return date.toLocaleDateString() + ' ' + date.toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'});
      }
      
      // Update the log display based on current filter
      function updateLogDisplay() {
        const visitorLog = JSON.parse(localStorage.getItem('visitorLog')) || [];
        
        // Update statistics
        totalVisitsElement.textContent = visitorLog.length;
        const uniqueVisitors = JSON.parse(localStorage.getItem('uniqueVisitors')) || [];
        uniqueVisitorsElement.textContent = uniqueVisitors.length;
        
        // Filter log entries based on current selection
        let filteredLog = visitorLog;
        
        if (currentFilter === 'today') {
          const today = new Date();
          today.setHours(0, 0, 0, 0);
          filteredLog = visitorLog.filter(entry => {
            const entryDate = new Date(entry.timestamp);
            return entryDate >= today;
          });
        } else if (currentFilter === 'week') {
          const weekAgo = new Date();
          weekAgo.setDate(weekAgo.getDate() - 7);
          filteredLog = visitorLog.filter(entry => {
            const entryDate = new Date(entry.timestamp);
            return entryDate >= weekAgo;
          });
        }
        
        // Display log entries
        if (filteredLog.length === 0) {
          logContainer.innerHTML = '<div class="log-empty">No visits to display</div>';
        } else {
          logContainer.innerHTML = filteredLog.map(entry => `
            <div class="log-entry">
              <span>${entry.isNew ? '🆕 ' : ''}Visitor ${entry.id.substring(0, 8)}...</span>
              <span class="log-time">${formatDate(entry.timestamp)}</span>
            </div>
          `).join('');
        }
      }
      
      // Set active button
      function setActiveButton(button) {
        document.querySelectorAll('.log-btn').forEach(btn => {
          btn.classList.remove('active');
        });
        button.classList.add('active');
      }
      
      // Event listeners for filter buttons
      showAllBtn.addEventListener('click', function() {
        currentFilter = 'all';
        setActiveButton(this);
        updateLogDisplay();
      });
      
      showTodayBtn.addEventListener('click', function() {
        currentFilter = 'today';
        setActiveButton(this);
        updateLogDisplay();
      });
      
      showWeekBtn.addEventListener('click', function() {
        currentFilter = 'week';
        setActiveButton(this);
        updateLogDisplay();
      });
      
      clearLogBtn.addEventListener('click', function() {
        if (confirm('Are you sure you want to clear the visitor log?')) {
          localStorage.removeItem('visitorLog');
          localStorage.removeItem('uniqueVisitors');
          localStorage.removeItem('visitorId');
          updateLogDisplay();
        }
      });
      
      // Initialize the visitor log
      initVisitorLog();
    });
  </script>
</body>
</html>
