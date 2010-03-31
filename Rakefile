task :default do
  execute <<-END
    git checkout gh-pages
    git merge master
    slideshow slides.md
    mv slides.html index.html
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
