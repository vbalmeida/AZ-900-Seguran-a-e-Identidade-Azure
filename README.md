# AZ-900-Seguran-a-e-Identidade-Azure

Identidade, acesso e segurança

Microsoft Entra ID:

O Microsoft Entra ID é um serviço de diretório que permite que você faça login e acesse tanto os aplicativos de nuvem da Microsoft quanto os aplicativos de nuvem que você desenvolver. Podemos vincular também ao Active Direct Local.


O que faz o Microsoft Entra ID?

Autenticação: Faz a verificação da identidade, redefinição de senha por autoatendimento, autenticação multifator, uma lista personalizada de senhas banidas e serviços de bloqueio inteligente.

Logon único (SSO): Permite que você com apenas um usuário e senha, realize o login em aplicativos.

Gerenciamento de Aplicativos: Gerencia seus aplicativos de nuvem e locais usando o Microsoft Entra ID. Recursos como Proxy de Aplicativo, aplicativos SaaS, o portal Meus Aplicativos e o logon único proporcionam uma experiência do usuário aprimorada.

Gerenciamento de dispositivos:  Permite que os dispositivos sejam gerenciados por meio de ferramentas como o Microsoft Intune. Também permite que políticas de Acesso Condicional baseadas no dispositivo restrinjam tentativas de acesso somente às provenientes de dispositivos conhecidos, independentemente da conta de usuário solicitante.

Como posso conectar o Microsoft Entra ID com o Active Directy Local?

Para essa conexão, posso utilizar dois métodos:
Microsoft Entra Connect: Onde ele sincroniza alterações entre os dois sistemas de identidade, de forma que você possa usar recursos como o SSO, a autenticação multifator e a redefinição de senha por autoatendimento em ambos.






O que é o Microsoft Entra Domain Server?

É um serviço que fornece serviços de domínio gerenciado, como ingresso no domínio, política de grupo, protocolo de acesso leve a diretórios (LDAP) e autenticação Kerberos/NTLM. 
Permite que você execute na nuvem aplicativos herdados que não podem usar métodos de autenticação modernos ou quando você não quiser que as pesquisas de diretório sempre retornem a um ambiente do AD DS local. 


Como funciona o Microsoft Entra Domain Server?

Preciso colocar um namespace exclusivo. Esse namespace é o nome do domínio. O conjunto de réplicas são dois controladores de domínio do Windows Server que são então implantados na região do Azure.

Um domínio gerenciado é configurado para executar uma sincronização unidirecional do Microsoft Entra ID para o Microsoft Entra Domain Services. É possível criar recursos diretamente no domínio gerenciado, mas eles não são sincronizados com o Microsoft Entra ID. Em um ambiente híbrido com um ambiente local do AD DS, o Microsoft Entra Connect sincroniza as informações de identidade com o Microsoft Entra ID, que, por sua vez, é sincronizado com o domínio gerenciado.


Autenticação: Requer que a pessoa, o serviço ou o dispositivo forneça algum tipo de credencial para provar quem são.

O Azure dá suporte a vários métodos de autenticação, incluindo senhas padrão, SSO (logon único), MFA (autenticação multifator) e métodos sem senha.

O SSO (logon único) permite que um usuário entre uma vez e use essa credencial para acessar vários recursos e aplicativos de provedores diferentes.
Melhora a segurança, já que quanto mais aplicativos usamos, mais credenciais precisamos lembrar.

Autenticação de Multifator (MFA): É quando além de colocarmos usuário e senha, precisa realizar uma verificação a mais. Exemplo: Confirmação de SMS, por e-mail, por aplicativo etc.

Autenticação sem Senha: Muitas vezes se torna frustrante para os usuários precisar sempre anotar senhas, por isso a autenticação sem Senha, utiliza algo que você tem. 


O Azure global e o Azure Government da Microsoft oferecem as três seguintes opções de autenticação sem senha que se integram ao Microsoft Entra ID:
Windows Hello para Empresas
Aplicativo Microsoft Authenticator
Chaves de segurança FIDO 2


Identidades externas do Azure
Uma identidade externa é uma pessoa, um dispositivo, um serviço etc. que está fora da sua organização. Se eles tiverem uma identidade digital emitida pela empresa ou pelo governo ou uma identidade social não gerenciada, como o Google ou o Facebook, eles poderão usar as próprias credenciais para entrar.
Podemos gerenciar esse acesso através dos aplicativos Microsoft Entra ID ou o Azure AD B2C.
As seguintes funcionalidades compõem identidades externas:
Colaboração B2B (Business to business): Deixando colaboradores externos acessarem os aplicativos empresariais da organização.
Conexão direta de B2B
Microsoft Azure Active Directory entre empresa e cliente (B2C)


Acesso condicional Azure
O Acesso Condicional é uma ferramenta que o Microsoft Entra ID usa para permitir (ou negar) o acesso a recursos baseados em sinais de identidade. Esses sinais incluem quem é o usuário, onde ele está e de qual dispositivo está solicitando acesso.
Um segundo fator de autenticação poderá não ser solicitado se o usuário estiver em uma localização conhecida. Caso o colaborador mude de local, será solicitado a autenticação. Outro sinal seria um aplicativo que o mesmo está tentando acessar.








Quando usar o acesso condicional:


Exigir a MFA para administradores, mas não para usuários regulares ou pessoas que se conectam de fora da rede corporativa.
Exigir acesso a serviços somente por meio de aplicativos cliente aprovados.
Exigir que os usuários acessem seu aplicativo somente de dispositivos gerenciados. 
Bloquear o acesso de fontes não confiáveis, como o acesso de locais desconhecidos ou inesperados.
Controle de acesso baseado em função no Azure:

Azure permite controlar o acesso por meio do RBAC do Azure (controle de acesso baseado em função do Azure).
O Azure fornece funções internas que descrevem regras de acesso comuns para os recursos de nuvem.
Quando você atribui indivíduos ou grupos a uma ou mais funções, eles recebem todas as permissões de acesso relacionadas.


Portanto, se você contratar um novo engenheiro e adicioná-lo ao grupo do RBAC do Azure para engenheiros, ele obterá automaticamente o mesmo acesso que os outros engenheiros do mesmo grupo do RBAC do Azure. Da mesma forma, se você adicionar outros recursos e apontar o RBAC do Azure para eles, todos nesse grupo do RBAC do Azure vão ter as permissões nos novos recursos, bem como nos recursos existentes.

Escopo: 

É um recurso ou um conjunto de recursos ao qual esse acesso se aplica.

Os escopos incluem:
Um grupo de gerenciamento (uma coleção de várias assinaturas).
Uma assinatura única.
Um grupo de recursos.
Um recurso individual.





O RBAC do Azure é hierárquico, porque quando você permite acesso a um escopo pai, essas permissões são herdadas por todos os filhos.

O RBAC do Azure é imposto em qualquer ação iniciada em um recurso do Azure que passa pelo Azure Resource Manager.
O Resource Manager é um serviço de gerenciamento que fornece um modo de organizar e proteger seus recursos de nuvem.
O RBAC do Azure não impõe permissões de acesso no nível do aplicativo nem dos dados. A segurança do aplicativo precisa ser realizada pelo aplicativo.
O RBAC do Azure usa um modelo de permissão.

Modelo de Confiança Zero:

A Confiança Zero é um modelo de segurança que pressupõe o pior cenário e protege os recursos com essa expectativa.
Em vez de supor que um dispositivo é seguro porque está dentro da rede corporativa, ele requer que todos se autentiquem. Em seguida, concede acesso com base na autenticação e não na localização.

Defesa em profundidade:

Proteger as informações, impedindo que elas sejam roubadas  por pessoas não autorizadas.

Camada de defesa em profundidade:

Cada camada fornece proteção, de modo que se uma camada for violada, uma camada seguinte já estará em vigor para impedir a exposição adicional.

A camada de segurança física é a primeira linha de defesa para proteger o hardware de computação no datacenter.
A camada de identidade e acesso controla o acesso à infraestrutura e ao controle de alterações.
A camada de perímetro usa a proteção contra DDoS (ataque de negação de serviço distribuído) para filtrar ataques em grande escala antes que eles possam causar uma negação de serviço para os usuários.
A camada de rede limita a comunicação entre recursos por meio de controles de acesso e segmentação.
A camada de computação protege o acesso a máquinas virtuais.
A camada de aplicativo ajuda a garantir que os aplicativos estejam seguros e livres de vulnerabilidades de segurança.
A camada de dados controla o acesso aos dados corporativos e do cliente que você precisa proteger.
Microsoft Defender

É uma ferramenta de monitoramento para gerenciamento da postura de segurança e proteção contra ameaças.
Ela já está integrada nativamente no Azure, por isso muitos serviços do Azure são monitorados e protegidos sem a necessidade de qualquer implantação.
Os recursos do GPSN (gerenciamento da postura de segurança na nuvem) são estendidos para computadores de várias nuvens sem a necessidade de agentes.
Ajuda a detectar ameaças em serviços Paas, Serviços de dados e Redes.

O Defender para Nuvem preenche três necessidades vitais à medida que você gerencia a segurança de seus recursos e cargas de trabalho locais e na nuvem:

Avaliação contínua: Conheça sua postura de segurança. Identifique e rastreie vulnerabilidades.


Proteger: Proteja recursos e serviços com o Azure Security Benchmark.

Defender: Detecte e resolva ameaças a recursos, cargas de trabalho e serviços.

Ao receber alertas de segurança,  em alguns casos, uma opção para disparar um aplicativo lógico em resposta.
