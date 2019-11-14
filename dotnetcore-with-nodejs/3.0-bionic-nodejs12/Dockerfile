FROM mcr.microsoft.com/dotnet/core/sdk:3.0-bionic

RUN apt-get update \
    && apt-get install -y curl gnupg build-essential \
    && curl --silent --location https://deb.nodesource.com/setup_12.x | bash - \
    && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get remove -y --purge cmdtest \
    && apt-get update \
    && apt-get install -y nodejs yarn \
    && apt-get install -y git git-lfs \
    # remove useless files from the current layer
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/lib/apt/lists.d/* \
    && apt-get autoremove \
    && apt-get clean \
    && apt-get autoclean
