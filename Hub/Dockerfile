# !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
# NOTE: DO *NOT* EDIT THIS FILE.  IT IS GENERATED.
# PLEASE UPDATE Dockerfile.txt INSTEAD OF THIS FILE
# !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
FROM selenium/base:3.8.1-bohrium
LABEL authors=SeleniumHQ

USER seluser

#========================
# Selenium Configuration
#========================

EXPOSE 4444

# As integer, maps to "maxSession"
ENV GRID_MAX_SESSION 5
# In milliseconds, maps to "newSessionWaitTimeout"
ENV GRID_NEW_SESSION_WAIT_TIMEOUT -1
# As a boolean, maps to "throwOnCapabilityNotPresent"
ENV GRID_THROW_ON_CAPABILITY_NOT_PRESENT true
# As an integer
ENV GRID_JETTY_MAX_THREADS -1
# In milliseconds, maps to "cleanUpCycle"
ENV GRID_CLEAN_UP_CYCLE 5000
# In seconds, maps to "browserTimeout"
ENV GRID_BROWSER_TIMEOUT 0
# In seconds, maps to "timeout"
ENV GRID_TIMEOUT 30
# Debug
ENV GRID_DEBUG false
# As integer, maps to "port"
ENV GRID_HUB_PORT 4444

COPY generate_config \
    entry_point.sh \
    /opt/bin/
# Running this command as sudo just to avoid the message:
# To run a command as administrator (user "root"), use "sudo <command>". See "man sudo_root" for details.
# When logging into the container
RUN /opt/bin/generate_config > /opt/selenium/config.json

CMD ["/opt/bin/entry_point.sh"]
