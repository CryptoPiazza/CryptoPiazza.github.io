# How to use

### Your picture
Add you picture to `assets/img/` and change the `image` entry in `_pages/about.md` accordingly.

### Change the configuration
Modify the configuration entries in `_config.yml`. 

### Add and modify your publications
Upload your `.bib` file in `_bibliography`. 
In `_config.yml`, in the Jekyll scholar section, change the name of the file accordingly.


In your BIB file you can set an entry to be a selected publication by adding the tag `selected = {true}`.

If you want to modify the sorting or other settings, modify the correct entries in the Jekyll scholar section of the `_config.yml` file.

### Modify your pages
You can modify your pages in `_pages`. Just write simple Markdown.



# Deployment

1. The name of your repository **MUST BE** `<your-github-username>.github.io` or `<your-github-orgname>.github.io`.
2. In `_config.yml`, set `url` to `https://<your-github-username>.github.io` and leave `baseurl` empty.
3. Set up automatic deployment of your webpage (see instructions below).
4. Make changes to your main branch, commit, and push!
5. After deployment, the webpage will become available at `<your-github-username>.github.io`.

## Enabling automatic deployment after push

1. Click on **Actions** tab and **Enable GitHub Actions**; do not worry about creating any workflows as everything has already been set for you.
2. Go to `Settings -> Actions -> General -> Workflow permissions`, and give `Read and write permissions` to GitHub Actions
3. Make any other changes to your webpage, commit, and push to your main branch. This will automatically trigger the **Deploy** action.
4. Wait for a few minutes and let the action complete. You can see the progress in the **Actions** tab. If completed successfully, in addition to the `main` branch, your repository should now have a newly built `gh-pages` branch. **Do NOT touch this branch!**
5. Finally, in the **Settings** of your repository, in the Pages section, set the branch to `gh-pages` (**NOT** to `main`). For more details, see [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source).

If you keep your site on another branch, open `.github/workflows/deploy.yml` **on the branch you keep your website on** and change `on->push->branches` and `on->pull\_request->branches` to the branch you keep your website on. This will trigger the action on pulls/pushes on that branch. The action will then deploy the website on the branch it was triggered from.


## Using your own domain instead of `<your-github-username>.github.io`

If own a certain domain (e.g. lucacampa.it) you can use it instead of the common github domain. 

### First step: On GitHub

1. On GitHub, navigate to your site's repository.

2. Under your repository name, click `Settings`. If you cannot see the `Settings` tab, select the dropdown menu, then click `Settings`.

3. In the `Code and automation` section of the sidebar, click Pages.

4. Under `Custom domain`, type your custom domain, then click `Save`. If you are publishing your site from a branch, this will create a commit that adds a **CNAME** file directly to the root of your source branch. If you are publishing your site with a custom GitHub Actions workflow, no CNAME file is created, so you need to create one manually (containing only a line of text with your custom domain). 

### Second step: on your DNS provider

1. To create `A` records, point your custom domain to the IP addresses for GitHub Pages.
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

2. [Verify your domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)

3. Optionally, to enforce HTTPS encryption for your site, select `Enforce HTTPS`. It can take up to 24 hours before this option is available. 


# On your local machine

`gem install jekyll bundler`

`bundle exec jekyll build`

`bundle exec jekyll serve`

