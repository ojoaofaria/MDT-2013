## MDT 2013
 Configuração MDT 2013

 Configurações para fazer backup do usuário e update do computador.

Coloque o arquivo UserExit.vbs no caminho:
\\path-to-deploy\scripts


# Sobre o arquivo de configuração 

// Esse parametro chama o arquivo "UserExit" e grava no nome do host.
    UserExit=UserExit.vbs
    OSDComputerName=#GetOfflineComputername()#

//  Esse conjunto de parametros definem onde e como salvar o backup do usuário.

    UserDataLocation=NETWORK
    UDShare=\\server_name\USMT
    UDDir=%OSDComputerName%

    ScanStateArgs=/v:5 /o /c
    USMTMigFiles001=MigApp.xml
    USMTMigFiles002=MigUser.xml

    LoadStateArgs=/v:5 /c /lac