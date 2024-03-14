- fiquei agarrado no último ponto "Altere a estratégia de navegação para utilizar os sensores ultrassônicos"
- vi que os sensores já estavam instalados no robô, mas eles não possuiam scripts
- pelo que entendi lendo a documentação, cada sensor deve ter um childScript dentro que envia as os dados
````python
#python
def sysCall_init(): 
	sim = require('sim') 
	simVision = require('simVision')
def sysCall_vision(inData): 
	simVision.sensorImgToWorkImg(inData['handle']) # copy the vision sensor image to the work image 
	simVision.edgeDetectionOnWorkImg(inData['handle'], 0.2) # perform edge detection on the work image 
	simVision.workImgToSensorImg(inData['handle']) # copy the work image to the vision sensor image buffer
````
- mas aparentemente para enviar para script externo, como fomos instruídos para utilizar precisamos de setar um nome para o sensor usando:
```python
sim.setStringSignal('hokuyo_range_data', sim.packFloatTable(dists))
sim.setStringSignal('hokuyo_angle_data', sim.packFloatTable(angles))
```
- primeira dúvida: o que o sensor deve retornar? workImg?
- segunda dúvida: quem deve setar o setStringSignal? todos os sensores individualmente ou devo criar um "manager" que recebe todos pelo script dentro do Coppelia e envia os dados formatados?
- terceira dúvida: não entendi a parte do sript da camera em que você multiplica dois vetores
- quarta dúvida: os sensores ultrassônicos enviam apenas a distancia do robo até um objeto?