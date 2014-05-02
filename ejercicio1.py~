import os
def CPUinfo():
# infofile on Linux machines:
  infofile = '/proc/cpuinfo'
  cpuinfo = {}
  if os.path.isfile(infofile):
    f = open(infofile, 'r')
    for line in f:
      try:
        name, value = [w.strip() for w in line.split(':')]
      except:
        continue
      if name == 'model name':
        cpuinfo['CPU type'] = value
      elif name == 'cache size':
        cpuinfo['cache size'] = value
      elif name == 'cpu MHz':
        cpuinfo['CPU speed'] = value + 'Hz'
      elif name == 'vendor_id':
        cpuinfo['vendor ID'] = value
    f.close()
  return cpuinfo
if __name__ == '__main__':
  print CPUinfo()
  
def SoftwareInfo():
  softinfo={}
  so=platform.platform()
  softinfo["S.O"]=so
  
  pv=platform.python_version()
  softinfo["python version"]=pv
  
  pd=platform.python_build()
  softinfo ["python date"]=pd[1]
  return softinfo
  
def SaveToFile(fn,d1,d2):
  f=open(fn,"w")
  f.write("Hardware\n")
  f.write("========\n")
  for clave in d1:
    f.write(clave)
    f.write("\t")
    f.write(d1[clave])
    f.write("\n")
    f.write("\n software\n")
    f.write("=======\n")
  for clave in d2:
    f.write(clave)
    f.write("\t")
    f.write(d2[clave])
    f.write("\n")
  f.close()
  
if __name__ == '__main__':
    cpui=CPUinfo ()
    si = SoftwareInfo ()
    print cpui
    print si
    filename="InfoPortatil.txt"
    SaveToFile(filename,cpui,si)
    print "informacion guardada en el fichero",filename
    
    
    
    
  