# Incident report: bad version v0.9.0

1. **What happened:** I put version `v0.9.0` on staging. It did not work. The logs showed the error `ERROR: missing required setting SECRET_KEY`.
2. **When I found out:** About 1 minute after the start (13:11:12), when the health check said "staging NOT healthy".
3. **What I did:** I read the logs to find the error. Then I went back to version `v1.0.0` with `IMAGE_TAG=v1.0.0` and `docker compose up -d`. I did not build anything again. The health check passed.
4. **How long the service was down:** About 3.5 minutes (13:11:12 to 13:14:39).
5. **How to stop this from happening again:** Run the health check automatically after each deployment, go back if it fails, and test every image before putting it on staging.
