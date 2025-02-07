FROM docker:27.5.1 AS runtime

RUN apk update && \
    apk upgrade && \
    apk add --no-cache git bash

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

##########################################################################
# Optional: Multi-stage build for a test environment using Bats.
#
# To enable the test environment, uncomment the block below.
##########################################################################

# FROM runtime as testEnv
# RUN apk add --no-cache coreutils bats
# COPY test.bats /test.bats
# COPY mock.sh /usr/local/bin/docker
# COPY mock.sh /usr/bin/date
# RUN /test.bats

FROM runtime
