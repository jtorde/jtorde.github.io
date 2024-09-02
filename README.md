# Instructions
(These instructions are for the github.io webpage)

Clone repo and do the following:
```bash
cd jtorde.github.io
bundle install  #(if you don’t do this, you get the error Could not find gem 'github-pages' in any of the gem sources listed in your Gemfile.)
bundle exec jekyll serve --watch #(this will run the webpage locally, it may take some time to run this command)
```
Go to http://localhost:4000/ (if you don't have a baseurl)  (see https://docs.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll)

Note that, for the github.io webpage, you need to have the line of `baseurl` commented (see [this](https://stackoverflow.com/a/64778847)). This is not the case for the mit.edu domain

Once you have done the necessary changes, commit them and push them to the remote repo. Github will automatically build the page, that will appear at https://jtorde.github.io/

# Old instructions 
(These instructions are for the mit.edu domain)

Install https://jekyllrb.com/docs/installation/

Click on the link of the "Looking for an example?" box of https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/


Clone repo
```bash
source ~/.bashrc
cd jtorde.github.io
bundle install  #(if you don’t do this, you get the error Could not find gem 'github-pages' in any of the gem sources listed in your Gemfile.)
bundle exec jekyll serve --watch #(this will run the webpage locally, it takes ~30seconds to run this command)
```
Go to http://localhost:4000/~jtorde/ , if you have baseurl=/~jtorde  or Go to http://localhost:4000/ (if you don't have a baseurl)  (see https://docs.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll)

-----------------------

## Prepare everything in Athena (only needed the first time you do it)

Hacer ssh en el athena del MIT:
https://web.mit.edu/dialup/www/ssh.html

Follow these steps:
https://kb.mit.edu/confluence/pages/viewpage.action?pageId=3907090



## Push to Athena
Once you have everything ready locally, do this: (taken from the section “deployment” of https://jekyllrb.com/docs/step-by-step/10-deployment/ )

```
bundle exec jekyll build
scp -r ./_site/* jtorde@ftp.dialup.mit.edu:/mit/jtorde/www
```

And that's all, wait ~ 2-3 min and everything should appear in http://www.mit.edu/~jtorde/

### Useful links
https://idratherbewriting.com/documentation-theme-jekyll/mydoc_push_build_to_server.html
https://jekyllrb.com/docs/step-by-step/10-deployment/
https://github.com/mmistakes/minimal-mistakes

### To redirect one page to another one, simply put this in the www folder of Athena:
```
<!DOCTYPE html>
  <html>
    <head>
  		<title>Old Page</title>
  			<meta charset="UTF-8" />
  			<meta http-equiv="refresh" content="1; URL=https://jtorde.github.io/" />
  	</head>
  	<body>
  		<p>This page has been moved. If you are not redirected within 1 seconds, click <a href="https://jtorde.github.io/">here</a> to go to the new homepage.</p>
  	</body>
  </html>
```

===============================================================

# Minimal Mistakes remote theme starter

Click [**Use this template**](https://github.com/mmistakes/mm-github-pages-starter/generate) button above for the quickest method of getting started with the [Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes).

Contains basic configuration to get you a site with:

- Sample posts.
- Sample top navigation.
- Sample author sidebar with social links.
- Sample footer links.
- Paginated home page.
- Archive pages for posts grouped by year, category, and tag.
- Sample about page.
- Sample 404 page.
- Site wide search.

Replace sample content with your own and [configure as necessary](https://mmistakes.github.io/minimal-mistakes/docs/configuration/).

---

## Troubleshooting

If you have a question about using Jekyll, start a discussion on the [Jekyll Forum](https://talk.jekyllrb.com/) or [StackOverflow](https://stackoverflow.com/questions/tagged/jekyll). Other resources:

- [Ruby 101](https://jekyllrb.com/docs/ruby-101/)
- [Setting up a Jekyll site with GitHub Pages](https://jekyllrb.com/docs/github-pages/)
- [Configuring GitHub Metadata](https://github.com/jekyll/github-metadata/blob/master/docs/configuration.md#configuration) to work properly when developing locally and avoid `No GitHub API authentication could be found. Some fields may be missing or have incorrect data.` warnings.
