This ia a sample project for gemfile not updating transient dependencies 

Steps to reproduce:
1) In Gemfile, we have one dependency named as "rubocop-airbnb"
2) Run renovate on this repo to update this dependency mentioned in Gemfile.
3) Added the renovate config also to update Gemfile.
4) After run the Gemfile not updating the related rubocop-airbnb transient deps like 

for example :

Current behaviour :

rubocop-airbnb (7.0.0)
      rubocop (~> 1.61) => 
      rubocop-performance (~> 1.20)
      rubocop-rails (~> 2.24)
      rubocop-rspec (~> 2.26)

rubocop (1.68.0)
      json (~> 2.3)
      language_server-protocol (>= 3.17.0)
      parallel (~> 1.10)
      parser (>= 3.3.0.2)
      rainbow (>= 2.2.2, < 4.0)
      regexp_parser (>= 2.4, < 3.0)
      rubocop-ast (>= 1.32.2, < 2.0) => update of this dependency available and its related transient deps also
      ruby-progressbar (~> 1.7)
      unicode-display_width (>= 2.4.0, < 3.0)

5) After renovate run it is not updating related transient deps.      


Expected behaviour :

It should update all the transient deps  like rubocop-ast this deps should also be updated like bundle update does. checked in local run.