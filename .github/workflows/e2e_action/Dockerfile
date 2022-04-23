FROM cypress/browsers:node16.14.0-slim-chrome99-ff97

# Update the dependencies to get the latest and greatest (and safest!) packages.
RUN apt update && apt upgrade -y

# avoid too many progress messages
# https://github.com/cypress-io/cypress/issues/1243
ENV CI=1 \
# disable shared memory X11 affecting Cypress v4 and Chrome
# https://github.com/cypress-io/cypress-docker-images/issues/270
  QT_X11_NO_MITSHM=1 \
  _X11_NO_MITSHM=1 \
  _MITSHM=0 \
  CYPRESS_CACHE_FOLDER=/root/.cache/Cypress

# should be root user
RUN echo "whoami: $(whoami)" \
  && npm config -g set user $(whoami) \
  && id \
  && npm install -g "cypress@9.5.4" \
  && cypress verify \
  && cypress cache path \
  && cypress cache list \
  && cypress info \
  && cypress version \
  && ls -la /root \
  && chmod 755 /root \
  && npm i -g yarn@latest \
  && node -p 'module.paths' \
  && cypress version \
  && echo  " node version:    $(node -v) \n" \
    "npm version:     $(npm -v) \n" \
    "yarn version:    $(yarn -v) \n" \
    "debian version:  $(cat /etc/debian_version) \n" \
    "user:            $(whoami) \n" \
    "chrome:          $(google-chrome --version || true) \n" \
    "firefox:         $(firefox --version || true) \n"

ENTRYPOINT ["cypress", "run"]