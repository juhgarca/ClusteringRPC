# ClusteringRPC
Modelagem em Redes de Petri Coloridas de protocolos de clustering para redes de sensores sem fio com captura de energia

--> generateNode.py
    Script Python que gera o arquivo com as fichas correspondentes aos nós. 
    
--> nodes.txt
    Arquivo gerado na execução de generateNode.py.
    
--> nodes2.txt
    Versão reduzida de nodes.txt.
    
--> projeto_v2_io.cpn
    Versão do projeto com leitura do arquivo de fichas, fonte de energia simples, seleção e anúncio de CH. 
    
--> projeto_v2_sem-fonte.cpn
    Versão do projeto com leitura do arquivo de fichas, seleção e anúncio de CH, sem fonte de energia para facilitar os testes.
    
--> rede_teste.cpn
    Versão simplificada do projeto, para implementação da parte de envio de mensagens.
    
    
ESTRUTURAS IMPORTANTES CRIADAS PARA O PROJETO

>> colset PACKET = product INT * REAL * INT * STRING;
    Pacote utilizado para troca de informações entre os nós. Variáveis correspondem a (id do emissor, distância entre emissor e receptor, id do receptor, mensagem).
    
>> colset RADIO = product REAL * LPACK;
    Corresponde ao rádio de cada nó. Formado por (potência do nó, buffer de entrada de pacotes).

>> colset NODE = product INT * REAL * REAL * REAL * RADIO * INT * INT declare output_col, input_ms;
    Estrutura do nó. Formado por (id, bateria, posição x, posição y, rádio, ch, número de vezes que foi CH).
