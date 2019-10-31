# ENGR-102-Group-Code
#temp_input = -10 degree C No value at that temperature
#temp_input = 60 degree C Volume: 0.0010149 m^3/kg Internal Engergy = 250.29 kJ/kg Enthapy = 255.36 kJ/kg Entropy = 0.8287 kJ/(kg K) 
#temp_input = 2 degree C Volume: 0.0009977 m^3/kgInternal Engergy: 0.04 kJ/kgEnthapy: 5.03 kJ/kgEntropy: 0.0001 kJ/(kg K)
#temp_input = 69 degree C Volume: 0.0010149 m^3/kgInternal Engergy: 250.29 kJ/kgEnthapy: 255.36 kJ/kgEntropy: 0.8287 kJ/(kg K)
#temp_input = 34 degree C Volume: 0.0009996 m^3/kgInternal Engergy: 83.61 kJ/kgEnthapy: 88.61 kJ/kgEntropy: 0.2954 kJ/(kg K)
with open("WaterData_5MPa.py","r") as myfile:    
    
    
    temp_input = int(input('Please enter your temperature: '))
#    def calculate(name, value_1, value_0, temp_1, temp_0, unit ): we try to use def but not succesful
#        value = (temp_input * (value_1 - value_0)/(temp_1-temp_0) + value_0
#        print('%s: %f %s.'%(name, value, unit))
    
    if (temp_input >= 0) and (temp_input <= 260) and (temp_input in tempC):
        for i in range(len(tempC)):
            if int(temp_input) == int(tempC[i]):
                print('Temperature:',tempC[i],'degree C')
                print('Volume:',v[i],'m^3/kg', end=' ')
                print('Internal Engergy:',u[i],'kJ/kg',end=' ')
                print('Enthapy:',h[i],'kJ/kg', end=' ')
                print('Entropy:',s[i],'kJ/(kg K)')
    elif (temp_input >= 0) and (temp_input <= 260) and (temp_input not in tempC) : 
        for i in range(len(tempC)):
            if ((temp_input - tempC[i]) < 20) and ((temp_input - tempC[i]) > 0):
                print('Temperature:', temp_input,'degree C')
                volume = (temp_input * ((v[i+1]-v[i]))/((tempC[i+1]-tempC[i])))  + v[i]
                print('Volume:',v[i],'m^3/kg', end=' ') 
                in_en = (temp_input * ((u[i+1]-u[i]))/((tempC[i+1]-tempC[i])))  + u[i]
                print('Internal Engergy:',u[i],'kJ/kg',end=' ')
                enthapy = (temp_input * ((h[i+1]-h[i]))/((tempC[i+1]-tempC[i])))  + h[i]
                print('Enthapy:',h[i],'kJ/kg', end=' ')  
                entropy = (temp_input * ((s[i+1]-s[i]))/((tempC[i+1]-tempC[i])))  + s[i]
                print('Entropy:',s[i],'kJ/(kg K)') 
    else:
        print('No value at that temperature.')
       
            
