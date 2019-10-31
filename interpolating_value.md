# ENGR-102-Group-Code
import csv
print('The purpose of this program is to provide thermo properties at 5Mpa or 10Mpa')


    
request = 'Yes'
while request == 'Yes' or request == 'yes':
    pressure = int(input('Enter your pressure: '))
    if (pressure == 5):
        with open ('ThermoProperties_5Mpa.csv','r') as myfile:
            five = csv.reader(myfile, delimiter = ',')    
            temp = [] #first row
            volume = [] #second row
            in_en = [] #third row
            enthapy = [] #forth row
            entropy = [] #fifth row
            for row in five:
                temp.append(float(row[0]))
                volume.append(float(row[1]))
                in_en.append(float(row[2]))
                enthapy.append(float(row[3]))
                entropy.append(float(row[4]))
            temp_input = int(input('Enter temperature: '))
            if temp_input in temp:
                for i in range(len(temp)):
                    if temp[i] == temp_input:
                        print('Temperature:',tempC[i],'degree C')
                        print('Volume:',v[i],'m^3/kg', end=' ')
                        print('Internal Engergy:',u[i],'kJ/kg',end=' ')
                        print('Enthapy:',h[i],'kJ/kg', end=' ')
                        print('Entropy:',s[i],'kJ/(kg K)')
            elif (temp_input not in temp) and (temp_input >= 0) and (temp_input <= 260):
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
                print('At 5Mpa, no value at this temperature.')
                
                
              
    elif (pressure == 10):
        with open ('ThermoProperties_10Mpa.csv','r') as myFile:
            ten = csv.reader(myFile, delimiter = ',')    
            temp = [] #first row
            volume = [] #second row
            in_en = [] #third row
            enthapy = [] #forth row
            entropy = [] #fifth row
            for row in ten:
                temp.append(float(row[0]))
                volume.append(float(row[1]))
                in_en.append(float(row[2]))
                enthapy.append(float(row[3]))
                entropy.append(float(row[4]))
            temp_input = int(input('Enter temperature: '))
            if temp_input in temp:
                for i in range(len(temp)):
                    if temp[i] == temp_input:
                        print('Temperature:',tempC[i],'degree C')
                        print('Volume:',v[i],'m^3/kg', end=' ')
                        print('Internal Engergy:',u[i],'kJ/kg',end=' ')
                        print('Enthapy:',h[i],'kJ/kg', end=' ')
                        print('Entropy:',s[i],'kJ/(kg K)')
            elif (temp_input not in temp) and (temp_input >= 0) and (temp_input <= 260):
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
                print('At 10Mpa, no value at this temperature.')
    else:
        print('Sorry. We only output at 5Mpa and 10Mpa.')
    
    request = str(input('Type \'Yes\' if you want to continue the interpolating. ' ))   

print('Thank you for using our service.')
    
