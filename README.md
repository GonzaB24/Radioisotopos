# Radioisotopos
Programacion en OpenMC la produccion de radioisotopos de Mo y Tc
 La intencion es de manera autonoma, estudiar acerca de la Mo-99 y su produccion para poder diseñar un programa que muestre de manera aproximada su produccion (Y si es posible hasta incluso una optimizacion de la misma). Para eso voy a basarme en libros de fisica nuclear, ingenieria nuclear,  programacion (openMC mediante metodo de montecarlo para transporte de neutrinos)
Voy a producirlo en Google Colab sin la necesidad de instalar programas debido a la computadora que uso xd: por lo tanto lo que tenes que hacer primero es instalar el open Mc que lo dejo a continuacion:

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

def install_openmc():
  %pip install -q condacolab
  import condacolab
  condacolab.install()
  !conda install -y -q -c conda-forge openmc
def install_data():
  import os
  if not os.path.isdir('/content'):
    print("Esta función instala los datos nucleares de OpenMC en una instancia de Google Colaboratory.")
    print("Para instalar localmente siga las instrucciones de la documentacion:")
    print("http://docs.openmc.org/en/stable/quickinstall.html")
    return
  %cd -q /content
  print("Obtaining HDF5 files...")
  %pip install -q openmc-data
  !download_endf -r b7.1
from time import time
t1 = time()
install_openmc()
install_data()
t2 = time()
print("Installed OpenMC in {:.2f} minutes".format((t2-t1)/60.0))

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

NOTA: actualmente me encuentro en la Etapa 2 (pienso llegar a una etapa final, calculo que seran 10 etapas aprox), en la que estoy usando solo Python y conocimientos basicos (ya que openMC requiere el uso de geometrias y matematicas y fisicas mas rigidas). Apunto a llegar a la Etapa 10 donde creo en lo personal, va a estar optimizado y hecho con openMC
