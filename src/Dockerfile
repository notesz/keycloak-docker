FROM quay.io/keycloak/keycloak:latest as builder

ARG KC_DB
ARG KC_DB_URL
ARG KC_DB_USERNAME
ARG KC_DB_PASSWORD
ARG KC_HOSTNAME
ARG KEYCLOAK_ADMIN
ARG KEYCLOAK_ADMIN_PASSWORD

####################
# Default settings #
####################
ENV KC_HEALTH_ENABLED=true
ENV KC_METRICS_ENABLED=true
ENV KC_FEATURES=token-exchange
ENV KC_DB=${KC_DB}

FROM quay.io/keycloak/keycloak:latest
COPY --from=builder /opt/keycloak/ /opt/keycloak/
WORKDIR /opt/keycloak

#####################
# Database settings #
#####################
ENV KC_DB_URL=${KC_DB_URL}
ENV KC_DB_USERNAME=${KC_DB_USERNAME}
ENV KC_DB_PASSWORD=${KC_DB_PASSWORD}

#####################
# Keycloak settings #
#####################
ENV KC_HOSTNAME=${KC_HOSTNAME}
ENV KC_PROXY=edge
ENV KEYCLOAK_ADMIN=${KEYCLOAK_ADMIN}
ENV KEYCLOAK_ADMIN_PASSWORD=${KEYCLOAK_ADMIN_PASSWORD}

#ENTRYPOINT ["/opt/keycloak/bin/kc.sh", "start"]
ENTRYPOINT ["/opt/keycloak/bin/kc.sh", "start --spi-theme-static-max-age=-1 --spi-theme-cache-themes=false --spi-theme-cache-templates=false"]
