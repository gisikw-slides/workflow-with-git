task :default do
  execute <<-END
    git checkout gh-pages
    git merge master
    slideshow slides.md
  END
  File.open("index.html","w"){|f|f.write(index <<-END
    SLIDESHOW!!
  END
  )}
  execute <<-END
    git add .
    git commit -am "Automated build"
    git push origin gh-pages
    git checkout master
  END
end

def execute(input)
  input.split("\n").each do |line|
    system(line.strip) unless line.empty?
  end
end

def index(contents)

<<-TEMPLATE
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
  <head>
    <title>Kevin W. Gisi</title>
    <link href="http://www.kevingisi.com/stylesheets/application.css" media="all" rel="stylesheet" type="text/css"/>
    <link href='http://www.kevingisi.com/favicon.ico' rel='shortcut icon' type='image/x-icon' />
    <script src='http://use.typekit.com/nzv8icd.js' type='text/javascript'></script>
    <script type='text/javascript'>
      try{Typekit.load();}catch(e){}
    </script>
  </head>
  <body>
    <div id='wrapper'>
      <div id='header'>
        <h1>
          <a href='http://www.kevingisi.com'>
            Kevin W. Gisi
          </a>
        </h1>
        <div id='header_description'>
          Ruby Developer
</div>
        <div id='contact_links'>
          <ul>
            <li>
              <a href='http://feeds.feedburner.com/kevingisi' id='rss'>RSS</a>
            </li>
            <li>
              <a href='http://twitter.com/gisikw' id='twitter'>Twitter</a>
            </li>
            <li>
              <a href='http://github.com/gisikw' id='github'>Github</a>
            </li>
            <li>
              <a href='http://www.workingwithrails.com/person/12637-kevin-gisi' id='wwr'>Working With Rails</a>
            </li>
          </ul>
        </div>
        <div class='clear'></div>
      </div>
      <div id='main'>
        <div id='left_pane'>
          <div class='datestamp page'></div>
          #{contents}
        </div>
        <div id='right_pane'>
          <h2 id='top'>Search</h2>
          <form action='http://www.google.com/search' id='searchform' method='get'>
            <input name='q' type='hidden' value='site:kevingisi.com' />
            <input name='q' size='15' type='text' />
            <input id='searchsubmit' type='submit' value='Search' />
          </form>
          <ul id='sidebar'>
            <li>
              <h2>Pages</h2>
              <ul>
                <li>
                  <a href="http://www.kevingisi.com">Home</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/about.html">About</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/presentations.html">Presentations</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/tutorials.html">Tutorials</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/projects.html">Projects</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/music.html">Music</a>
                </li>
                <li>
                  <a href="http://www.kevingisi.com/theatre.html">Theatre</a>
                </li>
              </ul>
            </li>
            <li>
              <h2>Recommended People</h2>
              <ul>
                <li>
                  <a href="http://benscofield.com/">Ben Scofield</a>
                </li>
                <li>
                  <a href="http://www.bphogan.com/">Brian P. Hogan</a>
                </li>
                <li>
                  <a href="http://www.rubberbandwound.com/">Chrisopher Warren</a>
                </li>
                <li>
                  <a href="http://blog.ninjahideout.com/">Darcy Laycock</a>
                </li>
                <li>
                  <a href="http://www.ethangunderson.com/">Ethan Gunderson</a>
                </li>
                <li>
                  <a href="http://www.blog.garycrabtree.com/">Gary Crabtree</a>
                </li>
                <li>
                  <a href="http://www.mikedubya.com/">Mike Weber</a>
                </li>
                <li>
                  <a href="http://nickplante.com/">Nick Plante</a>
                </li>
              </ul>
            </li>
            <li>
              <h2>Recommended Sites</h2>
              <ul>
                <li>
                  <a href="http://ecruby.org/">Eau Claire Ruby User Group</a>
                </li>
                <li>
                  <a href="http://www.railsmentors.org/">Rails Mentors</a>
                </li>
                <li>
                  <a href="http://railsrumble.com/">Rails Rumble</a>
                </li>
                <li>
                  <a href="http://www.wischess.org/">Wisconsin Chess Association</a>
                </li>
              </ul>
            </li>
            <li>
              <h2>Itinerary</h2>
              <div id='tripit-badge'>
                <script src='http://www.tripit.com/account/badge/id/6FBDEB0EAED5009210BA43353595D757/div_id/tripit-badge/badge.js' type='text/javascript'></script>
                <noscript>
                  <a href='http://www.tripit.com/'>
                    TripIt - Organize your travel
                  </a>
                </noscript>
              </div>
            </li>
          </ul>
        </div>
      </div>
      <div id='footer'>
        Powered by
        <a href='http://staticmatic.rubyforge.org'>StaticMatic,</a>
        <a href='http://disqus.com'>Disqus,</a>
        <a href='http://typekit.com'>Typekit,</a>
        <a href='http://tweetboard.com'>Tweetboard</a>
        and
        <a href='http://aws.amazon.com/cloudfront/'>Amazon Cloudfront</a>
        <br />
        Copyright &copy;
        2010
        Kevin W. Gisi
        |
        <a href='mailto:kevin@kevingisi.com'>
          kevin@kevingisi.com
        </a>
      </div>
      <script type='text/javascript'>
        //<![CDATA[
          //<![CDATA[
          (function() {
              var links = document.getElementsByTagName('a');
                var query = '?';
                  for(var i = 0; i < links.length; i++) {
                      if(links[i].href.indexOf('#disqus_thread') >= 0) {
                            query += 'url' + i + '=' + encodeURIComponent(links[i].href) + '&';
                              }
                                }
                                  document.write('<script charset="utf-8" type="text/javascript" src="http://disqus.com/forums/kevingisi/get_num_replies.js' + query + '"></' + 'script>');
          })();
          //]]>
        //]]>
      </script>
    </div>
  </body>
</html>
TEMPLATE
end
