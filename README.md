import React, { useState } from 'react';
import { Droplets, Shield, Users, Target, Briefcase, Mail, ChevronDown, Phone, MapPin } from 'lucide-react';

export default function AquaShieldWebsite() {
  const [activeSection, setActiveSection] = useState('inicio');

  const scrollToSection = (id) => {
    setActiveSection(id);
    document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 via-cyan-50 to-teal-50">
      {/* Header/Navigation */}
      <nav className="fixed top-0 w-full bg-white/90 backdrop-blur-md shadow-md z-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center space-x-2">
              <Droplets className="w-8 h-8 text-blue-600" />
              <span className="text-2xl font-bold bg-gradient-to-r from-blue-600 to-cyan-600 bg-clip-text text-transparent">
                AquaShield
              </span>
            </div>
            <div className="hidden md:flex space-x-6">
              {['Inicio', 'Servicios', 'Propuesta', 'Clientes', 'Equipo', 'Contacto'].map((item) => (
                <button
                  key={item}
                  onClick={() => scrollToSection(item.toLowerCase())}
                  className="text-gray-700 hover:text-blue-600 transition-colors font-medium"
                >
                  {item}
                </button>
              ))}
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="inicio" className="pt-24 pb-16 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="text-center">
            <div className="inline-block mb-6">
              <div className="flex items-center justify-center w-20 h-20 bg-gradient-to-br from-blue-500 to-cyan-500 rounded-full shadow-lg">
                <Shield className="w-10 h-10 text-white" />
              </div>
            </div>
            <h1 className="text-5xl md:text-6xl font-bold text-gray-900 mb-6">
              Transformando Inundaciones en
              <span className="block bg-gradient-to-r from-blue-600 to-cyan-600 bg-clip-text text-transparent">
                Oportunidades Sostenibles
              </span>
            </h1>
            <p className="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
              Protegemos tu hogar, institución o empresa mientras convertimos el agua estancada 
              en un recurso útil y económico para toda la comunidad.
            </p>
            <button 
              onClick={() => scrollToSection('contacto')}
              className="bg-gradient-to-r from-blue-600 to-cyan-600 text-white px-8 py-4 rounded-full font-semibold text-lg shadow-lg hover:shadow-xl transform hover:scale-105 transition-all"
            >
              Solicita una Evaluación Gratuita
            </button>
          </div>

          {/* Stats */}
          <div className="mt-16 grid grid-cols-1 md:grid-cols-3 gap-8">
            {[
              { label: 'Prevención de Inundaciones', value: '100%', icon: Shield },
              { label: 'Agua Reutilizada', value: 'Miles de Litros', icon: Droplets },
              { label: 'Comunidades Impactadas', value: 'Múltiples', icon: Users }
            ].map((stat, idx) => (
              <div key={idx} className="bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-shadow">
                <stat.icon className="w-8 h-8 text-blue-600 mb-3" />
                <div className="text-3xl font-bold text-gray-900 mb-2">{stat.value}</div>
                <div className="text-gray-600">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Historia */}
      <section className="py-16 px-4 sm:px-6 lg:px-8 bg-white">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-12 text-gray-900">Nuestra Historia</h2>
          <div className="bg-gradient-to-br from-blue-50 to-cyan-50 rounded-3xl p-8 md:p-12">
            <p className="text-lg text-gray-700 leading-relaxed mb-6">
              AquaShield surge para transformar un problema recurrente (las lluvias intensas, las aguas 
              estancadas y la afectación a hogares e instituciones) en una oportunidad de salud pública y 
              sostenibilidad.
            </p>
            <p className="text-lg text-gray-700 leading-relaxed">
              Desde el inicio integramos prevención de inundaciones, recolección y tratamiento de agua, 
              y educación comunitaria para fortalecer capacidades locales y reducir riesgos sanitarios y 
              ambientales. Hemos participado en iniciativas como Cartagena Ciudad Sostenible 2.0 y el 
              Reto Incuba CUEE, demostrando ser una empresa con una gran idea de transformación social.
            </p>
          </div>
        </div>
      </section>

      {/* Servicios */}
      <section id="servicios" className="py-16 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-4 text-gray-900">¿Qué Hacemos?</h2>
          <p className="text-center text-gray-600 mb-12 max-w-3xl mx-auto">
            Operamos un servicio integral de protección y gestión sostenible del agua
          </p>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {[
              {
                title: 'Recolección de Agua',
                description: 'Extraemos aguas estancadas con camiones especializados, reduciendo riesgos de inundación.',
                gradient: 'from-blue-500 to-blue-600'
              },
              {
                title: 'Tratamiento y Clasificación',
                description: 'Procesamos y clasificamos el agua según su calidad para diferentes usos responsables.',
                gradient: 'from-cyan-500 to-cyan-600'
              },
              {
                title: 'Barreras Portátiles',
                description: 'Comercializamos barreras contra inundaciones para proteger viviendas e instituciones.',
                gradient: 'from-teal-500 to-teal-600'
              },
              {
                title: 'Filtros Portátiles',
                description: 'Ofrecemos filtros con carbón activado y membranas para emergencias o consumo seguro.',
                gradient: 'from-blue-600 to-cyan-600'
              },
              {
                title: 'Redistribución',
                description: 'Suministramos agua clasificada a hogares, empresas e instituciones según calidad.',
                gradient: 'from-cyan-600 to-teal-600'
              },
              {
                title: 'Educación Comunitaria',
                description: 'Capacitamos y dejamos habilidades instaladas en la comunidad para gestión sostenible.',
                gradient: 'from-teal-600 to-blue-600'
              }
            ].map((service, idx) => (
              <div key={idx} className="bg-white rounded-2xl p-6 shadow-lg hover:shadow-2xl transition-all transform hover:-translate-y-2">
                <div className={`w-12 h-12 bg-gradient-to-br ${service.gradient} rounded-xl mb-4 flex items-center justify-center`}>
                  <Droplets className="w-6 h-6 text-white" />
                </div>
                <h3 className="text-xl font-bold text-gray-900 mb-3">{service.title}</h3>
                <p className="text-gray-600">{service.description}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Propuesta de Valor */}
      <section id="propuesta" className="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-blue-600 to-cyan-600 text-white">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-12">
            <Target className="w-16 h-16 mx-auto mb-6" />
            <h2 className="text-4xl font-bold mb-6">Nuestra Propuesta de Valor</h2>
            <p className="text-xl text-blue-100 max-w-3xl mx-auto">
              Reducir pérdidas por inundaciones, mejorar la salud y la resiliencia urbana, 
              y facilitar el aprovechamiento sostenible del agua
            </p>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {[
              {
                title: 'Recolección',
                description: 'Capturamos aguas estancadas antes de que causen daños'
              },
              {
                title: 'Clasificación',
                description: 'Tratamos y categorizamos el agua según calidad y uso'
              },
              {
                title: 'Suministro',
                description: 'Redistribuimos para usos potables, domésticos o industriales'
              }
            ].map((item, idx) => (
              <div key={idx} className="bg-white/10 backdrop-blur-sm rounded-2xl p-6 hover:bg-white/20 transition-all">
                <h3 className="text-2xl font-bold mb-3">{item.title}</h3>
                <p className="text-blue-100">{item.description}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Clientes */}
      <section id="clientes" className="py-16 px-4 sm:px-6 lg:px-8 bg-white">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-4 text-gray-900">¿A Quién Servimos?</h2>
          <p className="text-center text-gray-600 mb-12 max-w-3xl mx-auto">
            Acompañamos a diversos sectores en su camino hacia la sostenibilidad y la prevención
          </p>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            {[
              {
                tipo: 'Hogares',
                descripcion: 'Especialmente en zonas en condiciones especiales que requieren protección contra inundaciones'
              },
              {
                tipo: 'Instituciones Educativas',
                descripcion: 'Colegios, universidades y centros educativos que buscan sostenibilidad'
              },
              {
                tipo: 'Sector Salud',
                descripcion: 'Hospitales y centros médicos que necesitan continuidad operativa'
              },
              {
                tipo: 'Empresas',
                descripcion: 'Hoteles, constructoras, industrias y centros comerciales'
              },
              {
                tipo: 'Gobiernos Locales',
                descripcion: 'Entidades públicas con programas de agua segura y gestión del riesgo'
              },
              {
                tipo: 'ONGs',
                descripcion: 'Organizaciones con proyectos de impacto social y ambiental'
              }
            ].map((cliente, idx) => (
              <div key={idx} className="bg-gradient-to-br from-blue-50 to-cyan-50 rounded-xl p-6 border-l-4 border-blue-600 hover:shadow-lg transition-shadow">
                <h3 className="text-xl font-bold text-gray-900 mb-2">{cliente.tipo}</h3>
                <p className="text-gray-600">{cliente.descripcion}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Proceso */}
      <section className="py-16 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-4 text-gray-900">Cómo Trabajamos</h2>
          <p className="text-center text-gray-600 mb-12 max-w-3xl mx-auto">
            Un proceso integral basado en datos para garantizar calidad y trazabilidad
          </p>
          <div className="space-y-8">
            {[
              {
                paso: '1',
                titulo: 'Diagnóstico y Planificación',
                descripcion: 'Realizamos un análisis técnico completo y diseñamos la ruta óptima de intervención'
              },
              {
                paso: '2',
                titulo: 'Succión y Transporte',
                descripcion: 'Ejecutamos la recolección del agua estancada con equipos especializados'
              },
              {
                paso: '3',
                titulo: 'Tratamiento',
                descripcion: 'Filtramos, desinfectamos y clasificamos con sensores de flujo, presión y detección de químicos'
              },
              {
                paso: '4',
                titulo: 'Almacenamiento',
                descripcion: 'Guardamos en tanques compartimentados para asegurar logística y calidad'
              },
              {
                paso: '5',
                titulo: 'Entrega y Capacitación',
                descripcion: 'Suministramos el agua y dejamos capacidades instaladas en la comunidad'
              }
            ].map((proceso, idx) => (
              <div key={idx} className="flex items-start space-x-4">
                <div className="flex-shrink-0 w-12 h-12 bg-gradient-to-br from-blue-600 to-cyan-600 rounded-full flex items-center justify-center text-white font-bold text-xl">
                  {proceso.paso}
                </div>
                <div className="flex-1 bg-white rounded-xl p-6 shadow-md">
                  <h3 className="text-xl font-bold text-gray-900 mb-2">{proceso.titulo}</h3>
                  <p className="text-gray-600">{proceso.descripcion}</p>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Aliados */}
      <section className="py-16 px-4 sm:px-6 lg:px-8 bg-white">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-4 text-gray-900">Socios y Aliados</h2>
          <p className="text-center text-gray-600 mb-12 max-w-3xl mx-auto">
            Trabajamos con organizaciones clave para garantizar calidad y expansión regional
          </p>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {[
              {
                tipo: 'Universidades y Centros de Investigación',
                rol: 'Validan impactos y aceleran el desarrollo tecnológico'
              },
              {
                tipo: 'Instituciones Educativas',
                rol: 'Sensibilización y formación comunitaria'
              },
              {
                tipo: 'Fabricantes de Sensores y Tanques',
                rol: 'Garantizan fiabilidad operativa del sistema'
              },
              {
                tipo: 'Sector Logístico y Entidades Públicas',
                rol: 'Escalan cobertura y capacidad de respuesta'
              }
            ].map((aliado, idx) => (
              <div key={idx} className="bg-gradient-to-br from-cyan-50 to-teal-50 rounded-xl p-6 hover:shadow-lg transition-shadow">
                <Briefcase className="w-8 h-8 text-blue-600 mb-3" />
                <h3 className="text-xl font-bold text-gray-900 mb-2">{aliado.tipo}</h3>
                <p className="text-gray-600">{aliado.rol}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Equipo */}
      <section id="equipo" className="py-16 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-12">
            <Users className="w-16 h-16 mx-auto mb-6 text-blue-600" />
            <h2 className="text-4xl font-bold mb-4 text-gray-900">Nuestro Equipo</h2>
            <p className="text-gray-600 max-w-3xl mx-auto">
              Un equipo multidisciplinario que integra ingeniería, operación de campo y educación comunitaria
            </p>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            {[
              {
                nombre: 'Vanessa Sofía Diago Rodríguez',
                rol: 'Ingeniería y Optimización del Proyecto',
                descripcion: 'Lidera la optimización de procesos técnicos y mejora continua del sistema'
              },
              {
                nombre: 'Juan Daniel Jácome Yáñez',
                rol: 'Ingeniería de Planta',
                descripcion: 'Gestiona las operaciones técnicas de recolección, tratamiento y distribución del agua'
              },
              {
                nombre: 'Yosueth David Cárdenas Velasco',
                rol: 'Marketing y Ventas',
                descripcion: 'Desarrolla estrategias comerciales y gestiona la relación con clientes y aliados'
              },
              {
                nombre: 'Ruddy Rodríguez Romero',
                rol: 'Recursos Humanos',
                descripcion: 'Coordina el talento humano y fortalece las capacidades del equipo'
              },
              {
                nombre: 'Károlay Palafor Cantillo',
                rol: 'Operaciones de Campo',
                descripcion: 'Supervisa la ejecución en terreno y la logística de recolección y entrega'
              },
              {
                nombre: 'Kareylis González Cardona',
                rol: 'Educación Comunitaria',
                descripcion: 'Diseña programas de capacitación y sensibilización para las comunidades'
              }
            ].map((miembro, idx) => (
              <div key={idx} className="bg-white rounded-xl p-6 shadow-lg hover:shadow-xl transition-shadow">
                <div className="w-16 h-16 bg-gradient-to-br from-blue-600 to-cyan-600 rounded-full mx-auto mb-4 flex items-center justify-center text-white font-bold text-xl">
                  {miembro.nombre.split(' ').map(n => n[0]).join('').slice(0, 2)}
                </div>
                <h3 className="font-bold text-gray-900 text-lg text-center mb-2">{miembro.nombre}</h3>
                <p className="text-blue-600 font-semibold text-center mb-3">{miembro.rol}</p>
                <p className="text-gray-600 text-sm text-center">{miembro.descripcion}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contacto */}
      <section id="contacto" className="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-blue-600 to-cyan-600 text-white">
        <div className="max-w-4xl mx-auto text-center">
          <Mail className="w-16 h-16 mx-auto mb-6" />
          <h2 className="text-4xl font-bold mb-6">¿Listo para Proteger tu Espacio?</h2>
          <p className="text-xl text-blue-100 mb-8">
            ¿Tu hogar, empresa o institución necesita prevención de inundaciones o agua clasificada 
            para uso responsable?
          </p>
          <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 mb-8">
            <h3 className="text-2xl font-bold mb-6">Agenda una Evaluación Gratuita</h3>
            <p className="text-blue-100 mb-6">
              Llevamos la solución completa desde el diagnóstico hasta la operación y el mantenimiento
            </p>
            <div className="space-y-4">
              <button className="w-full bg-white text-blue-600 px-8 py-4 rounded-xl font-semibold text-lg shadow-lg hover:shadow-xl transform hover:scale-105 transition-all">
                Contáctanos Ahora
              </button>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-white py-12 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto text-center">
          <div className="flex items-center justify-center space-x-2 mb-4">
            <Droplets className="w-8 h-8 text-blue-400" />
            <span className="text-2xl font-bold">AquaShield</span>
          </div>
          <p className="text-gray-400 mb-4">
            Transformando problemas en oportunidades sostenibles
          </p>
          <p className="text-sm text-gray-500">
            © 2025 AquaShield. Todos los derechos reservados.
          </p>
        </div>
      </footer>
    </div>
  );
}
