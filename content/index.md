---
aliases: 
title: index
tags:
  - meta
---

# Index

## Getting Started

### Setting Up Your Environment

1. **Create a GitHub Account:**
   - If you don't already have a GitHub account, sign up at [GitHub](https://github.com/signup). Follow the prompts to complete the registration process.
2. **Install Git:**
   - Download Git from [Git SCM](https://git-scm.com/downloads). Choose the version compatible with your operating system and follow the installation instructions.
3. **Install Obsidian:**
   - Visit the [Obsidian download page](https://obsidian.md/) and select the installer for your operating system. Run the installer and follow the on-screen instructions to install Obsidian.

### Setting Up Your Workspace

4. **Download the Vault Template:**
   - Navigate to the [vault-template repository](https://github.com/indravajra/vault-template/) on my GitHub.
   - Click on the "Code" button, then select "Download ZIP" to download the vault template.

![[_bin/images/index/6d7095727023a17f74b5e2f1c0c733d8_MD5.jpeg|Image of the "Download ZIP" button]]

5. **Extract the Vault Template:**
   - Once downloaded, locate the `vault-template-main.zip` file in your downloads folder or the location you chose to save it.
   - Use a file extraction tool like [7-Zip](https://www.7-zip.org/) or your operating system’s built-in tool to extract the contents of the ZIP file.
   - Consider renaming the extracted folder from `vault-template-main` to `vault` for simplicity.
6. **Opening Your Vault in Obsidian:**
   - Launch Obsidian, then click on the “Open folder as vault” option.
   - Navigate to the directory where you extracted the vault template and select the “content” directory.

![[_bin/images/index/aaa655c82a6097736ac7fa1859c45bba_MD5.jpeg|Image of the "Open folder as vault" option]]

## Important Note on Directory Structure and Setup:

When you extract the `vault-template-main.zip` file, it's crucial to ensure that the directory structure aligns with the intended organization for both Obsidian and the Quartz digital garden setup. Follow these steps if you encounter an additional nested directory:

1. **Navigate to the Extracted Directory:**
   - Open the first-level directory that was created during the extraction process, which might be named something like `vault-template-main`.
3. **Rename the Directory:**
   - Rename the `vault-template-main` to just `vault` at the top level, to align with the structure detailed below.
#### Directory Structure:

Your directory should ideally look like this, with `content` directly under `vault` and the `quartz` directory alongside:

```bash
vault/
├── content/          # Your Obsidian notes and resources
│   ├── 00 Journal/
│   ├── 01 Projects/
│   ├── 02 Areas/
│   ├── 03 Resources/
│   ├── 04 Archives/
│   ├── 05 Canvas/
│   ├── _bin/
│   └── _inbox/
└── quartz/           # Code and configuration for Quartz digital garden
    ├── cli/
    ├── components/
    ├── i18n/
    ├── plugins/
    ├── processors/
    ├── static/
    ├── styles/
    └── util/
```

- The `content` directory is where all your Obsidian notes and resources are organized. It contains various subdirectories for different categories like `Journal`, `Projects`, `Areas`, etc.
- The `quartz` directory holds the code and configuration files necessary for setting up your digital garden with Quartz, which we'll publish to GitHub Pages later. For more information on Quartz, refer to the [Quartz 4 documentation](https://quartz.jzhao.xyz/).

# Making Notes

## Hotkeys/Workflows

| Hotkey          | What it does                                                |
| :-------------- | :---------------------------------------------------------- |
| `Ctrl + N`      | Create a new untitled note in the root of the vault         |
| `Ctrl + Enter`  | Generate metadata for a newly created note using `Ctrl + N` |
| `Shift + Enter` | Open link under cursor in a new tab                         |
| `Alt + M`       | Move the current note to a folder                           |
|                 | Show Outline(Table of Contents based on headings)           |
| `Alt + Q`       | Toggle Emoji Toolbar        😇                              |
| `Alt + T`       | Open template modal                                         |

## Some Rules to Abide by

- Use tags to organize your notes and make it easier to find specific notes later on. For example, you might use tags to label notes by project or goal, or to indicate the type of information contained in each note.
- Tags are always plural
- Use only a  few designated amount of tags, they should be clearly defined and no tag should overlap with another in terms of what they mean to preserve ontology of the wiki.
- Create a separate note for each area of focus and use backlinks to connect the notes together. This will help you see the connections between different notes and make it easier to navigate between them. Perhaps tag an area of focus as an `#areas`.

## PARA

- **Projects**: This folder will contain notes related to specific projects you are working on. For example, if you are working on a book, you might have a folder called "Book Project" where you store all of your notes and ideas related to the book.
- **Areas**: This folder will contain notes related to broad areas of your life or work. For example, you might have an "Fitness" folder where you store all of your notes and ideas related to staying healthy and fit.
- **Resources**: This folder will contain notes that serve as references or resources for other notes in your second brain. For example, you might have a folder called "Research" where you store articles, books, and other resources that you want to use as references for your own ideas and projects.
- **Archives**: This folder will contain notes that are no longer actively used but you want to keep for reference. For example, you might have an "Ideas" folder where you store ideas that you came up with but are no longer working on.

> [!note]
> When creating a new note, think about how it fits into the overall structure of your second brain. For example, if you have a note about a new workout routine that you want to try, you might store it in the "Fitness" folder in the "Areas" section of your second brain.

## Why PARA

1.  P: Project-Based: Organize your information around specific projects or goals. This can help you focus your efforts and see the big picture.
2.  A: Areas: Divide your projects into smaller areas of focus. This can help you break down complex tasks into manageable chunks and make progress on each part of a project.
3.  R: Resources: Collect and organize the resources you need to complete your projects. This can include things like notes, documents, links, and other materials.
4.  A: Actions: Identify the specific actions you need to take to complete each project and track your progress. This can help you stay on track and make sure that you are making progress on your projects.

## Setup Backup and Deployment on Github

We’re using Github for the backup of your notes and for deployment/publishing of your digital garden we’re using GitHub Pages:

### Configuring Your Digital Garden

1. **Update Configuration:**
   - Navigate to `vault/quartz.config.js` within your local directory.
   - Modify the configuration parameters to reflect your digital garden's specifics:
     ```javascript
     pageTitle: "Your Digital Garden's Name", // Replace with the name of your digital garden
     ...
     baseUrl: "https://your-github-username.github.io/repo-name", // Replace with your GitHub Pages URL
     ```
   - Ensure the `baseUrl` matches the pattern `https://<your-github-username>.github.io/<repo-name>`, where `<repo-name>` is the name of your GitHub repository.
   - For further configuration of the look and feel of your digital garden, visit [Quartz 4 Documentation](https://quartz.jzhao.xyz/).

### Creating a Repository on GitHub

2. **Create a New Repository:**
   - Visit [https://github.com/new](https://github.com/new) to initiate a new repository.
   - Name your repository, which will serve as the `baseUrl` mentioned in the `quartz.config.js` file.

![[_bin/images/index/1503a223c36bc380d087910f188ab1c5_MD5.jpeg]]

3. **Configure GitHub Pages:**
   - In your repository's settings, locate the **Build and deployment** section within the **Pages** settings.
   - Set the **Source** to “GitHub Actions” to utilize the provided GitHub Actions workflow for deployment.

![[_bin/images/index/2a94b215b030831ab19816dc7c18f1ba_MD5.jpeg]]

### Initializing Local Repository and Pushing to GitHub

4. **Initialize Local Git Repository:**
   - Open your terminal or command line interface and navigate to the `vault` directory.
   - Execute the following commands to initialize your repository and stage your files:
     ```bash
     git init
     git add -A
     git commit -m "Initial commit"
     ```

5. **Configure Git User:**
   - If not already configured, set your Git username and email:
     ```bash
     git config --global user.name "Your GitHub Username"
     git config --global user.email "your_email@example.com"
     ```
   - These should match your GitHub account details for seamless integration.

6. **Link Remote Repository:**
   - Connect your local repository to the remote GitHub repository:
     ```bash
     git remote add origin https://github.com/<your-username>/<repo-name>.git
     ```
   - Replace `<your-username>` and `<repo-name>` with your GitHub username and the name of your repository, respectively.

7. **Push to GitHub:**
   - Push your commits to the remote repository and set the upstream branch to `main`:
     ```bash
     git push -u origin main
     ```
   - This action will trigger the GitHub Actions workflow, automatically building and deploying your digital garden to GitHub Pages.

### Completion

Upon successful deployment, your digital garden will be accessible at `https://<your-github-username>.github.io/<repo-name>`. 

Congratulations on setting up your digital garden and integrating it with your Obsidian note-taking system!

**Optional:** For those preferring a graphical interface, consider using Visual Studio Code's Git integration to commit and push changes to your repository. This can simplify the process for users less comfortable with command-line operations.

---
## Plugins

I installed some quality of life plugins(community).

| Name                                                                                               | Author                                                                                                   | Description                                                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Templater**](https://obsidian.md/plugins?id=templater-obsidian)                                 | [SilentVoid](https://github.com/SilentVoid13)                                                            | A template system for Obsidian that supports dynamic expressions and automation for efficient note-taking.                                                                                   |
| [**Auto Note Mover**](https://obsidian.md/plugins?id=auto-note-mover)                              | [faru](https://github.com/farux/)                                                                        | Automatically moves notes to specified folders based on customizable rules, helping to maintain an organized vault.                                                                          |
| [**BRAT**](https://obsidian.md/plugins?id=obsidian42-brat)                                         | [TfTHacker](https://github.com/TfTHacker/obsidian42-brat)                                                | Provides a reusable actions toolkit to enhance Obsidian's functionality with custom buttons, menus, and more for improved workflow efficiency.                                               |
| [**Strange New Worlds (SNW)**](https://github.com/TfTHacker/obsidian42-strange-new-worlds)         | [TfTHacker](https://twitter.com/TfTHacker)                                                               | An extension of BRAT offering additional customizations and features for advanced users looking to further tailor their Obsidian experience.                                                 |
| [**Auto Link Title**](https://obsidian.md/plugins?id=obsidian-auto-link-title)                     | [Matt Furden](https://github.com/zolrath)                                                                | Automatically retrieves and inserts the title of linked web pages into your notes for more informative and readable links.                                                                   |
| [**Smart Typography**](https://obsidian.md/plugins?id=obsidian-smart-typography)                   | [mgmeyers](https://github.com/mgmeyers/obsidian-smart-typography)                                        | Enhances note readability and aesthetics by automatically converting straight quotes to curly quotes, dashes to em/en dashes, and more.                                                      |
| [**Completr**](https://obsidian.md/plugins?id=obsidian-completr)                                   | [tth05](https://github.com/tth05)                                                                        | Provides advanced autocomplete functionality within your notes, including suggestions for words, links, and more, based on your vault's content.                                             |
| [**Automatically reveal active file**](https://obsidian.md/plugins?id=obsidian-reveal-active-file) | [Matt Sessions](https://www.matthewsessions.com)                                                         | Ensures the file explorer always highlights and scrolls to the active note, making navigation easier in larger vaults.                                                                       |
| [**Dataview**](https://obsidian.md/plugins?id=dataview)                                            | [Michael Brenan](https://github.com/blacksmithgu)                                                        | Allows for querying, filtering, and displaying data from your notes in tables, lists, or task boards, enabling powerful data management and analysis within your vault.                      |
| [**Emoji Toolbar**](https://obsidian.md/plugins?id=obsidian-emoji-toolbar)                         | [oliveryh](https://github.com/oliveryh/obsidian-emoji-toolbar)                                           | Adds a convenient emoji picker to Obsidian, making it easy to insert emojis into your notes for added expressiveness and visual flair.                                                       |
| [**PodNotes**](https://obsidian.md/plugins?id=podnotes)                                            | [Christian B. B. Houmann](https://bagerbach.com)                                                         | Facilitates taking detailed and structured notes on podcasts within Obsidian, including features for timestamps, metadata, and more.                                                         |
| [**Wikipedia**](https://obsidian.md/plugins?id=obsidian-wikipedia)                                 | [Jonathan Miller](https://jmill.dev)                                                                     | Enables seamless integration with Wikipedia, allowing you to search and reference Wikipedia articles directly from within Obsidian.                                                          |
| [**Periodic PARA**](https://obsidian.md/plugins?id=periodic-para)                                  | [YiBing Lin](https://quanru.github.io)                                                                   | Implements the PARA method (Projects, Areas, Resources, Archives) in Obsidian, providing templates and organizational structures to manage your notes according to this productivity system. |
| [**Easy toggle sidebars**](https://obsidian.md/plugins?id=easy-toggle-sidebars)                    | [1C0D](https://github.com/1C0D/)                                                                         | Offers simple keyboard shortcuts or buttons to quickly toggle the visibility of sidebars, enhancing your note-taking workspace's flexibility.                                                |
| [**QuickAdd**](https://obsidian.md/plugins?id=quickadd)                                            | [Christian B. B. Houmann](https://bagerbach.com)                                                         | Enhances productivity by allowing you to quickly add content to your notes through customizable choices, macros, and templates.                                                              |
| [**Omnivore**](https://obsidian.md/plugins?id=obsidian-omnivore)                                   | [Omnivore](https://github.com/omnivore-app)                                                              | A plugin aimed at researchers, allowing for efficient extraction, annotation, and management of information from various sources directly into Obsidian.                                     |
| [**Local Images Plus**](https://obsidian.md/plugins?id=obsidian-local-images-plus)                 | [catalysm, aleksey-rezvov, Sergei Korneev](https://github.com/Sergei-Korneev/obsidian-local-images-plus) | Helps manage images in your notes by downloading external images to your vault and optimizing image links for local access, ensuring your notes are self-contained.                          |
| [**Book Search**](https://obsidian.md/plugins?id=obsidian-book-search-plugin)                      | [anpigon](https://github.com/anpigon)                                                                    | Facilitates searching for books and retrieving metadata, which can be directly inserted into your notes for easy reference and cataloging.                                                   |
| [**Git**](https://obsidian.md/plugins?id=obsidian-git)                                             | [Vinzent03](https://ko-fi.com/vinzent)                                                                   | Integrates Git version control into Obsidian, allowing for automatic backups and versioning of your vault to a Git repository.                                                               |
| [**Style Settings**](https://obsidian.md/plugins?id=obsidian-style-settings)                       | [mgmeyers](https://github.com/mgmeyers/obsidian-style-settings)                                          | Provides a user-friendly interface for adjusting and customizing the appearance of themes and plugins that support style settings, enhancing personalization.                                |
| [**Home tab**](https://obsidian.md/plugins?id=home-tab)                                            | [Renso](https://github.com/olrenso)                                                                      | Adds a customizable "Home" tab to Obsidian, giving you quick access to key notes, resources, or dashboards for efficient navigation.                                                         |
| [**Homepage**](https://obsidian.md/plugins?id=homepage)                                            | [novov](https://novov.me)                                                                                | Allows you to set a specific note as your startup page, so you can start your Obsidian session with an overview, dashboard, or any note of your choice.                                      |
| [**Linter**](https://obsidian.md/plugins?id=obsidian-linter)                                       | [Victor Tao](https://github.com/platers)                                                                 | Automatically formats and tidies up your notes based on customizable rules, helping to maintain consistency and readability across your vault.                                               |
| [**Folder notes**](https://obsidian.md/plugins?id=folder-notes)                                    | [Lost Paul](https://github.com/LostPaul)                                                                 | Allows you to create and manage notes that are directly associated with folders, turning them into index or overview notes for the content within those folders.                             |
| [**Minimal Theme Settings**](https://obsidian.md/plugins?id=obsidian-minimal-settings)             | [@kepano](https://www.twitter.com/kepano)                                                                | Extends the Minimal theme with additional customization options, allowing for a highly personalized and clean writing environment.                                                           |
| [**Telegram Sync**](https://obsidian.md/plugins?id=telegram-sync)                                  | [soberhacker](https://github.com/soberhacker/obsidian-telegram-sync)                                     | Enables synchronization of notes and content between Obsidian and Telegram, facilitating mobile note-taking and sharing.                                                                     |
| [**Share Note**](https://obsidian.md/plugins?id=share-note)                                        | [Alan Grainger](https://github.com/alangrainger)                                                         | Provides a simple way to share Obsidian notes with others, including options for public sharing and exporting to different formats.                                                          |

## Templates


> [!NOTE] Insert Template Modal 
> Use the shortcut `Alt + T` to open the Insert Template Modal, you can change this from the `Hotkeys` tab under Obsidian Settings.

### VOMIT Journal Prompt

This template can be accessed from [[VOMIT journal prompt]], it is essentially from the YouTube [The Journaling System that changed my life](https://www.youtube.com/watch?v=U8RQsJ0Q3Mo&pp=ygUXdm9taXQgbWV0aG9kIGpvdXJuYWxpbmc%3D) by [struthless](https://www.youtube.com/@struthless).

### Periodic Notes Templates

The templates for the Periodic Notes can be found under `00 Journal/Templates` folder.

![[_bin/images/index/d575cbea9b90f2aba12d5898b4e960db_MD5.jpeg]]


## Book Notes

For creating book notes, we’re leveraging the Book Search plugin, the template for this can found at [[book search plugin template]].

## Random Journal Prompt

I borrowed this from somewhere which I am unable to recall, this template will basically give you three random journal prompts from the list of questions stored in the `vault/content/_bin/wordlist.10000.txt` file, you can’t view this file in Obsidian, use your file manager to access it.

## Podcasts

Leveraging the PodNotes plugin, open command palette `ctrl + p` and select `PodNotes: Create Podcast Note` or by selecting an episode from the Podcast player on the right sidebar.

![[Pasted image 20221109092901.png]]

To add a podcast to the podcast player, simply get the RSS feed link to your podcast and add it from the PodNotes plugin settings.

## Other Tools

- [Omnivore is a complete, open source read-it-later solution for people who like reading.](https://omnivore.app/)
- [NattyNote: Take time-stamped YouTube notes](https://github.com/ahmedelq/NattyNote)