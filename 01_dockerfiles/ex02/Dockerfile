FROM ruby
RUN apt-get update &&                           \
    apt-get install -y nodejs sqlite3 &&    \
	gem install rails

# Expose le port 3000 pour accéder à l'app.
ONBUILD EXPOSE  3000
# Copie tout le contenu du dossier courant dans le container
ONBUILD COPY    . /opt/app
# Definie le dossier d'ouverture au lancement du container
ONBUILD WORKDIR /opt/app
 # Installe les dépendances à partir du Gemfile de l'app
ONBUILD RUN bundle install
# Met la structure de la bdd à jour à partir d'un fichier de app/db/migrate/
ONBUILD RUN rails db:migrate
# Remplit la bdd à partir du fichier app/db/seeds.rb
ONBUILD RUN rails db:seed

# bundle install --jobs 20 -> Run 20 downloads simultaneously
# #
#
# ########## SAMPLE APPS
# # https://github.com/mhartl/sample_app
# # https://github.com/RailsApps/rails-signup-thankyou
#
# ########## LAUNCH APP
# # Clone app in ex02
# # In app folder (/app), copy/paste Dockerfile from subject
# # In ex02 folder, run : docker build -t ft-rails:on-build .
# # In /app folder, run : docker build -t myapp -f Dockerfile .
# # docker run -p 3000:3000 --rm myapp
