Microblx.org: Documentation about Microblx Framework
---------------------------------------

## Instruction on how to add/modify the webpage

### Add/modify contents:

- The pages published over github are static HTML files.
- You are free to add material directly with HTML files (use less css as possible), or by Markdown file (extension ".md")
- The layout of pure HTML files is up to you, while Markdown files will be parsed automatically and a HMTL page will be generated using the layout you indicated.
- Always remember to add the header in the Markdown file. The only field mandatory is "layout" (which layout you want to use, default layout is "page").
- Other layouts are possible, under request (or you can create one!)
- Please, follow the "tab" organization when you add contents to the webpage. That is, the documentation is divided into __Documentation__ folder and __Tutorial__ folder. Add your material there.
- If your documentation is simple (only one page, no images), add it directly in the folder (__Documentation__ or __Tutorials__)
- if your documentation is "complex" (contains more than one page/markdown file, contains pictures), then create a subfolder!
- To add an image, create again another subfolder with same name of your page, and store your image, while the .md files lies outside.
- In case of doubts, check the existing pages or ask!

### Workflow

- Fork this repository
- Make your changes/commit new material
- Test your tutorial, make sure the related software is available
- Check the rendering of the Markdown files in
- Commit the changes on your own repository
- Send a pull-request
- Your material will be added!

### Try the webpage locally
Normally, Markdown files should be rendered just fine. However, you can check the result locally by installing ___jekyll___ toolchain (https://github.com/jekyll/jekyll).
(This includes ruby and the gems: jekyll, nokogiri, ...)
NOTE: Nokogiri is not in the dependencies. To install it run 
```
$ sudo gem install nokogiri
```
Once you have it on your computer, go to the repository root and run

```sh
$ jekyll serve -w --baseurl ''
```


