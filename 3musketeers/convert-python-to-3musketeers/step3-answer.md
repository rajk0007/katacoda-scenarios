    version: '3'
    services:
      printvars:
          build: .
          image: printvars-compose:latest
          environment:
            - DOG_BREED=HUSKY

