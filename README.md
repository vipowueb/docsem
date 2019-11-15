docsem Project
==============

Contributing to the website
---------------------------

**Note**    Major issues or feature requests should be filed on the [issue tracker](https://github.com/vipowueb/docsem/issues) first.


### Build Requirements and Instructions

You will need:
 - [Ruby](https://www.ruby-lang.org/) - Jekyll is written in Ruby
 - [Bundler](http://bundler.io/) - a package manager for Ruby. Install it by running `ruby gem install bundler`

After forking and cloning the repository, you have to run the following commands:
(1) `bundle install` - downloads the required libraries
(2) `bundle exec jekyll serve` - builds the website and runs a local webserver on port 4000

The site should now be running locally:
![website](https://github.com/vipowueb/docsem/blob/master/index_page.png)


General
-------

All HTML pages will be generated automatically by Jekyll. How to add [PhD Away Days entries](#create-a-PhD-Away-Days-entry), [new semester entries](#create-a-new-semester-entry) and [new talks](#create-a-new-talk) is described below. 

Talks are added separately, see [create a new talk](#create-a-new-talk), and will be included automatically in the semester overview page and can therefore be linked as single pages as well. The convention is `/talks/20yy/mm/dd/lastname.html`.

PhD Away Days are added separately, see [create a new semester entries](#create-a-new-semester-entry), and will be included automatically in the semester overview page and can therefore be linked as single pages as well. The convention `/away_days/yyyy.html`.


Repository structure
--------------------

- `_away_days` - contains the source pages and data (as markdown files for the PhD Away Days by year, see [Create a PhD Away Days entry](#create-a-PhD-Away-Days-entry)
- `_f` - contains files linked on pages. In particular, the programme and slides of the PhD Away Days as PDFs.
- `_fonts` - contains the fontawesome font files
- `_gfx` - contains graphics
- `_includes` - contains HTML snippets to be included via `{% include file.html %}` in other pages and the layouts
- `_layouts` - contains the layouts used in pages. Layouts can be inherited, the root layout is `default.html`.
- `_sass` - contains the stylesheet sass files to layout the pages
- `_semester` - contains the source pages and data (as markdown files) for each semester, see [Create a new semester entry](#create-a-new-semester-entry)
- `_site` - the output of the generated site is stored here by default, this folder only exists after Jekyll built the site
- `_talks` - contains the source pages and data (as markdown files for each talk given, see [Create a new talk](#create-a-new-talk)
- `css` - contains the main stylesheet


Create a PhD Away Days entry
----------------------------

The PhD seminar is replaced by the PhD Away Days once per year, normally for the winter semester. The Away Days will be included automatically in the semester overview page, but can be linked as single pages as well. The convention is `/away_days/yyyy.html`.

Following the `/_away_days/_template.md` only two keys `layout` and `semesterYear` are necassary for sorting and creating the PhD Away Days section on the semester overview page. So, if the PhD Away Days have not been yet fixed after the summer semester seminar started, just use the blank template file:
```
---
layout:                 away_days
semesterYear:           20yy-01-01
---
The dates and location have not been fixed yet.
```

Create a copy the Markdown file `_template_.md` and rename that file following the file name convention: `year.md`. Make sure not to include special characters in the file name. The file name (= corresponding year) will be used as title and link text. Then open the renamed file you renamed and adjust the self explaning values. Abstracts should be put into a folder `/f/_away_daysYYYY/` following the directory structure.

```
---
layout:                 away_days
semesterYear:           yyyy-01-01
title:                  202X &ndash; 202X
from:                   yyyy-mm-dd
to:                     yyyy-mm-dd
location:               "Venue, City, Country"
organiser:
    - name: "Robert Baumgarth"
      url: "http://math.uni.lu/~baumgarth"
    - name: "Organiser 2"
      url: "link-to-organiser"
supervisors:
    - name: "name #X"
    - name: "name #X"
abstractsLink:          /f/away_days202X/202X-PhDAwayDays_Abstracts.pdf
---
Sample text: This year's PhD Away Days were organised in cooperation with 
the PhD candidates of the [Université de Bordeaux][1]{:target="_blank"}. 

[1]: https://www.u-bordeaux.fr/formation/PRLIMA_110/licence-mathematiques
```


Create a new semester entry
---------------------------

Core sites are the semester overview pages. They include all talks filtered by year. They can be linked by the convention `/semester/yyyy.html`.

Create a copy the Markdown file `_template_.md` and rename that file following the file name convention: `year.md`. Make sure not to include special characters in the file name. The file name (= corresponding year) will be used as title and link text. Then open the renamed file you renamed and adjust the self explaning values. 

```
---
layout:                 semester
semesterYear:           yyyy-01-01
day:                    Thursday
from:                   "11:00"
to:                     "12:00"
location:               "MSA 3.230 (Maison Du Savoir) on Campus Belval"
organiser:
    - name: Vincent Pecastaing
      url: http://www.normalesup.org/~pecastai/
    - name: "Yannick Voglaire"
      url: http://uni-lu.academia.edu/YannickVoglaire
organisationalMeeting:  yyyy-mm-dd
---
```


Create a new talk
-----------------

Talks will be included automatically in the semester overview page, but can be linked as single pages as well.

Create a copy the Markdown file `_20yy-mm-dd-NAME.md` and rename that file following the file name convention: `year-mm-dd-lastname.md`. Make sure not to include special characters in the file name. The file name will be used for sorting, creating the SEO optimised link `/talks/20yy/mm/dd/lastname.html`. Then open the renamed file you renamed and adjust the self explaning values. 

```
---
layout:     talk
title:      "I can be a longer title"
speaker:    first_name LAST_NAME
categories: talks
---
Abstract...
```

License
-------

The project is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. [CC-BY 4.0][1].

[1]: https://creativecommons.org/licenses/by/4.0/