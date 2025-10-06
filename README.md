# Netlify Next.js + Contentful Minimal Starter

![Screenshot](https://assets.stackbit.com/docs/tutorial-shared-thumb.png)

**⚡ View demo:** [nextjs-contentful-starter.netlify.app](https://nextjs-contentful-starter.netlify.app/)

## Prerequisites

Before you begin, please make sure you have the following:

- [Netlify account](https://www.netlify.com/)
- [Contentful account](https://www.contentful.com/)
- GitHub, GitLab or Bitbucket account
- Node v18+ or later
- (optional) [nvm](https://github.com/nvm-sh/nvm) for Node version management.

## Getting Started

### Clone this repository

Fork and clone your repository, then run `npm install` in its root directory.

### Create Contentful Space

After signing into Contentful, create a new space. 

### Generate Management Token

If you don't already have a management token (or _personal access token_), generate one. To do so, go into your new empty space, then:

1. Click _Settings_
1. Choose _API Keys_
1. Select the _Content management tokens_ tab
1. Click the button to generate a new token

![Generate content management token](./docs/generate-mgmt-token.png)

### Generate Preview & Delivery API Keys

From the same place you generated the management token, you can now generate API access keys.

1. Select the *content delivery / preview tokens* tab
1. Choose *Add API key*

### Set Environment Variables

In your project, duplicate `.env.example` to `.env`. 

Fill in the values in the file based on the keys you've created. 

Note: the Contentful space ID can be viewed and copied via *Settings->General Settings* in Contentful.

### Import Content

Import the provided content models & content into Contentful by running the `import.js` script:

    npm run import

If the import fails to run, make sure that you've run `npm install` and that all keys in your `.env` file are set correctly.

### Run the Website

Run the Next.js development server:

    npm run dev

Visit [localhost:3000](http://localhost:3000) and you should see the example content you imported into your new Contentful space.

### Run Netlify Visual Editor in Local Development Mode

Keep the Next.js development server running, and open a new command-line window in the same directory.

Install Stackbit's CLI tools (once):
    
    npm i -g @stackbit/cli@latest

Run the CLI:

    stackbit dev

Click the displayed link to [localhost:8090/_stackbit](http://localhost:8090/_stackbit) and the visual editor will open.

### Create a Cloud-Based Netlify Project

To deploy a cloud-based Netlify project your need to connected your repository to Netlify:

1. If you haven't created your GitHub project repository, create it and push your code to GitHub
2. Open the [app.netlify.com](https://app.netlify.com/), and choose "Import from Git" in the "Import an existing project" section
3. In the "Configure site and deploy" step you will see the "Visual editor" section. To make it work, you will need to install "Netlify Visual Editor GitHub App" in your GitHub account.
4. Deploy your project

## Next Steps

Here are a few suggestions on what to do next if you're new to Netlify visual editor:

- Learn [how Netlify visual editor works](https://docs.netlify.com/visual-editor/overview/)
- Check [Netlify visual editor reference documentation](https://visual-editor-reference.netlify.com/)

## Support

If you get stuck along the way, get help in our [support forums](https://answers.netlify.com/).
ForkplayWebsite/
│
├─ index.html        ← Main page
├─ style.css         ← Styling
├─ script.js         ← Animations & interactions
├─ images/           ← Put your logos, hero image, menu pics here
│     ├─ logo.png
│     ├─ hero.jpg
│     └─ menu1.jpg (optional)
└─ fonts/            ← Optional custom fonts
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Forkplay Soul Menu</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- HEADER / NAV -->
    <header>
        <nav>
            <img src="images/logo.png" alt="Forkplay Logo" class="logo">
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <img src="images/hero.jpg" alt="Forkplay Hero" class="hero-img">
        <div class="hero-text">
            <h1>Where Soul Food Meets Late-Night Luxury</h1>
            <p>Delicious portions, unforgettable flavors.</p>
        </div>
    </section>

    <!-- ABOUT SECTION -->
    <section id="about" class="about">
        <h2>About Forkplay</h2>
        <p>Forkplay brings you soul food with a late-night twist. Fresh, flavorful, and always made with love.</p>
    </section>

    <!-- MENU SECTION -->
    <section id="menu" class="menu">
        <h2>Our Menu</h2>
        <div class="menu-grid">
            <!-- Example item -->
            <div class="menu-item">
                <h3>Fried Chicken Pan</h3>
                <p>Price: $40</p>
            </div>
            <div class="menu-item">
                <h3>BBQ Ribs Pan</h3>
                <p>Price: $75</p>
            </div>
            <div class="menu-item">
                <h3>Family Feast Pan</h3>
                <p>Price: $130</p>
            </div>
            <!-- Add more items here -->
        </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact" class="contact">
        <h2>Contact Us</h2>
        <p>Email: hello@forkplay.com</p>
        <p>Instagram: @ForkplayATL</p>
    </section>

    <script src="script.js"></script>
</body>
</html>
/* GENERAL */
body {
  margin: 0;
  font-family: 'Arial', sans-serif;
  background-color: #fff;  /* Use your background color from Lovable */
  color: #333;             /* Main text color */
}

/* HEADER */
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 40px;
  background-color: #fff;  /* Change if Lovable header is colored */
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.logo {
  height: 60px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 30px;
}

.nav-links li a {
  color: #ff4d6d; /* Lovable pink accent */
}

.nav-links li a:hover {
  color: #ff1a4d; /* Darker hover pink */
}

/* HERO */
.hero {
  position: relative;
  text-align: center;
  color: white;
}

.hero-img {
  width: 100%;
  height: 500px;
  object-fit: cover;
  filter: brightness(60%);
}

.hero-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* ABOUT */
.about {
  padding: 60px 20px;
  text-align: center;
}

/* MENU */
.menu {
  padding: 60px 20px;
  background-color: #f9f9f9; /* Light section background */
}

.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  max-width: 1000px;
  margin: 0 auto;
}

.menu-item {
  background-color: #fff;
  padding: 20px;
  text-align: center;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.menu-item img {
  width: 100%;
  border-radius: 10px;
  margin-bottom: 10px;
}

/* CONTACT */
.contact {
  padding: 60px 20px;
  text-align: center;
}
// Smooth scrolling for nav links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function(e) {
    e.preventDefault();
    document.querySelector(this.getAttribute('href')).scrollIntoView({
      behavior: 'smooth'
    });
  });
});
