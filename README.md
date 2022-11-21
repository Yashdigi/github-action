
java
  name: Code signing with Secure Software Manager 

  on: push 

  jobs:
    build:
      strategy:
        matrix:
          os: [ubuntu-latest, windows-latest]

      runs-on: ${{ matrix.os }}

      steps:
       - name: Code signing with Secure Software Manager 
         uses: digicert/ssm-code-signing@latest-version 
      env:
        SM_API_KEY: ${{secrets.SM_API_KEY}} 
        SM_CLIENT_CERT_PASSWORD: ${{secrets.SM_CLIENT_CERT_PASSWORD}} 
        SM_CLIENT_CERT_FILE: ${{secrets.SM_CLIENT_CERT_FILE}}
