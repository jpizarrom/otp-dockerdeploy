#
# OpenTripPlanner Dockerfile
#
# https://github.com/opentripplanner/opentripplanner
#

# Start with a small Ubuntu base image
FROM java:8

# Let's download the jar file
RUN \
  mkdir /var/otp && \
  cd /var/otp && \
  wget -q -O /var/otp/otp.jar http://maven.conveyal.com.s3.amazonaws.com/org/opentripplanner/otp/0.20.0/otp-0.20.0-shaded.jar

# Expose ports for other containers
EXPOSE 8080
EXPOSE 8081

VOLUME [ "/var/otp/data" ]

ENTRYPOINT [ "java", "-Xmx1G", "-Xverify:none", "-jar", "/var/otp/otp.jar" ]

CMD [ "--help" ]
