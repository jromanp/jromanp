import React, { useState, useEffect } from 'react';
import { Github, Linkedin, Mail, ExternalLink, Code, Briefcase, GraduationCap, Award, ChevronDown } from 'lucide-react';

export default function Portfolio() {
  const [activeSection, setActiveSection] = useState('home');
  const [scrolled, setScrolled] = useState(false);

  useEffect(() => {
    const handleScroll = () => {
      setScrolled(window.scrollY > 50);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const projects = [
    {
      title: "E-commerce Platform",
      description: "Plataforma completa de comercio electrónico con React, Node.js y MongoDB",
      tech: ["React", "Node.js", "MongoDB", "Stripe"],
      link: "#"
    },
    {
      title: "Task Management App",
      description: "Aplicación de gestión de tareas con autenticación y tiempo real",
      tech: ["Next.js", "Firebase", "Tailwind CSS"],
      link: "#"
    },
    {
      title: "Weather Dashboard",
      description: "Dashboard meteorológico con APIs externas y visualización de datos",
      tech: ["Vue.js", "Chart.js", "OpenWeather API"],
      link: "#"
    },
    {
      title: "Social Media Analytics",
      description: "Herramienta de análisis de redes sociales con reportes personalizados",
      tech: ["Angular", "D3.js", "Express"],
      link: "#"
    }
  ];

  const skills = [
    { name: "React", level: 90 },
    { name: "Next.js", level: 85 },
    { name: "TypeScript", level: 88 },
    { name: "Tailwind CSS", level: 92 },
    { name: "Node.js", level: 80 },
    { name: "Angular", level: 75 },
    { name: "Vue.js", level: 78 },
    { name: "MongoDB", level: 82 }
  ];

  const experience = [
    {
      role: "Senior Frontend Developer",
      company: "Tech Solutions Inc.",
      period: "2022 - Present",
      description: "Desarrollo de aplicaciones web escalables con React y TypeScript"
    },
    {
      role: "Full Stack Developer",
      company: "Digital Innovations",
      period: "2020 - 2022",
      description: "Construcción de plataformas SaaS con arquitectura moderna"
    },
    {
      role: "Junior Developer",
      company: "StartupLab",
      period: "2019 - 2020",
      description: "Desarrollo frontend y mantenimiento de aplicaciones existentes"
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 text-white">
      {/* Navigation */}
      <nav className={`fixed top-0 w-full z-50 transition-all duration-300 ${scrolled ? 'bg-slate-900/95 backdrop-blur-sm shadow-lg' : 'bg-transparent'}`}>
        <div className="container mx-auto px-6 py-4">
          <div className="flex justify-between items-center">
            <h1 className="text-2xl font-bold bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
              Portfolio
            </h1>
            <div className="hidden md:flex space-x-8">
              {['Home', 'About', 'Projects', 'Skills', 'Contact'].map((item) => (
                <button
                  key={item}
                  onClick={() => setActiveSection(item.toLowerCase())}
                  className="hover:text-purple-400 transition-colors duration-300"
                >
                  {item}
                </button>
              ))}
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="min-h-screen flex items-center justify-center relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-r from-purple-500/10 to-pink-500/10 animate-pulse"></div>
        <div className="container mx-auto px-6 text-center relative z-10">
          <div className="mb-8 inline-block">
            <div className="w-32 h-32 bg-gradient-to-br from-purple-500 to-pink-500 rounded-full flex items-center justify-center text-4xl font-bold shadow-2xl animate-float">
              JD
            </div>
          </div>
          <h1 className="text-5xl md:text-7xl font-bold mb-6 animate-fade-in">
            Hola, soy <span className="bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">John Doe</span>
          </h1>
          <p className="text-xl md:text-2xl text-gray-300 mb-8 animate-fade-in-delay">
            Full Stack Developer | Especialista en React & Node.js
          </p>
          <div className="flex justify-center space-x-4 mb-12">
            <a href="#" className="bg-purple-600 hover:bg-purple-700 px-8 py-3 rounded-full transition-all duration-300 hover:scale-105 shadow-lg">
              Ver Proyectos
            </a>
            <a href="#" className="border-2 border-purple-400 hover:bg-purple-400/20 px-8 py-3 rounded-full transition-all duration-300 hover:scale-105">
              Contactar
            </a>
          </div>
          <div className="flex justify-center space-x-6">
            <a href="#" className="hover:text-purple-400 transition-colors duration-300 hover:scale-110 transform">
              <Github size={28} />
            </a>
            <a href="#" className="hover:text-purple-400 transition-colors duration-300 hover:scale-110 transform">
              <Linkedin size={28} />
            </a>
            <a href="#" className="hover:text-purple-400 transition-colors duration-300 hover:scale-110 transform">
              <Mail size={28} />
            </a>
          </div>
        </div>
        <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
          <ChevronDown size={32} className="text-purple-400" />
        </div>
      </section>

      {/* About Section */}
      <section className="py-20 bg-slate-900/50">
        <div className="container mx-auto px-6">
          <h2 className="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Sobre Mí
          </h2>
          <div className="grid md:grid-cols-2 gap-12 items-center">
            <div>
              <p className="text-lg text-gray-300 mb-6">
                Soy un desarrollador apasionado por crear experiencias web excepcionales. Con más de 5 años de experiencia en el desarrollo de aplicaciones modernas, me especializo en construir interfaces intuitivas y eficientes.
              </p>
              <p className="text-lg text-gray-300 mb-6">
                Mi enfoque está en utilizar las últimas tecnologías como React, Next.js, Angular y Vue.js para crear soluciones escalables que resuelvan problemas reales.
              </p>
              <div className="flex space-x-4">
                <div className="flex items-center space-x-2">
                  <Award className="text-purple-400" />
                  <span>5+ años experiencia</span>
                </div>
                <div className="flex items-center space-x-2">
                  <Code className="text-purple-400" />
                  <span>50+ proyectos</span>
                </div>
              </div>
            </div>
            <div className="grid grid-cols-2 gap-4">
              {['React', 'Next.js', 'TypeScript', 'Tailwind'].map((tech, i) => (
                <div key={i} className="bg-gradient-to-br from-purple-600/20 to-pink-600/20 p-6 rounded-lg backdrop-blur-sm border border-purple-500/20 hover:scale-105 transition-transform duration-300">
                  <h3 className="font-bold text-xl mb-2">{tech}</h3>
                  <p className="text-gray-400">Expert Level</p>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Projects Section */}
      <section className="py-20">
        <div className="container mx-auto px-6">
          <h2 className="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Proyectos Destacados
          </h2>
          <div className="grid md:grid-cols-2 gap-8">
            {projects.map((project, index) => (
              <div key={index} className="group bg-slate-800/50 rounded-xl p-6 backdrop-blur-sm border border-purple-500/20 hover:border-purple-500/50 transition-all duration-300 hover:scale-105 hover:shadow-2xl hover:shadow-purple-500/20">
                <div className="flex justify-between items-start mb-4">
                  <Briefcase className="text-purple-400" size={32} />
                  <a href={project.link} className="text-purple-400 hover:text-purple-300 transition-colors">
                    <ExternalLink size={24} />
                  </a>
                </div>
                <h3 className="text-2xl font-bold mb-3 group-hover:text-purple-400 transition-colors">
                  {project.title}
                </h3>
                <p className="text-gray-400 mb-4">{project.description}</p>
                <div className="flex flex-wrap gap-2">
                  {project.tech.map((tech, i) => (
                    <span key={i} className="px-3 py-1 bg-purple-600/20 rounded-full text-sm border border-purple-500/30">
                      {tech}
                    </span>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Skills Section */}
      <section className="py-20 bg-slate-900/50">
        <div className="container mx-auto px-6">
          <h2 className="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Habilidades Técnicas
          </h2>
          <div className="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto">
            {skills.map((skill, index) => (
              <div key={index} className="space-y-2">
                <div className="flex justify-between">
                  <span className="font-semibold">{skill.name}</span>
                  <span className="text-purple-400">{skill.level}%</span>
                </div>
                <div className="h-3 bg-slate-700 rounded-full overflow-hidden">
                  <div 
                    className="h-full bg-gradient-to-r from-purple-500 to-pink-500 rounded-full transition-all duration-1000 ease-out"
                    style={{ width: `${skill.level}%` }}
                  ></div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Experience Section */}
      <section className="py-20">
        <div className="container mx-auto px-6">
          <h2 className="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Experiencia Profesional
          </h2>
          <div className="max-w-3xl mx-auto space-y-8">
            {experience.map((exp, index) => (
              <div key={index} className="relative pl-8 border-l-2 border-purple-500/30 hover:border-purple-500 transition-colors duration-300">
                <div className="absolute -left-2 top-0 w-4 h-4 bg-purple-500 rounded-full"></div>
                <div className="bg-slate-800/50 rounded-lg p-6 backdrop-blur-sm border border-purple-500/20 hover:border-purple-500/50 transition-all duration-300 hover:scale-102">
                  <div className="flex items-center space-x-2 mb-2">
                    <GraduationCap className="text-purple-400" size={24} />
                    <h3 className="text-xl font-bold">{exp.role}</h3>
                  </div>
                  <p className="text-purple-400 mb-2">{exp.company}</p>
                  <p className="text-gray-400 text-sm mb-3">{exp.period}</p>
                  <p className="text-gray-300">{exp.description}</p>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section className="py-20 bg-slate-900/50">
        <div className="container mx-auto px-6 text-center">
          <h2 className="text-4xl font-bold mb-8 bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            ¿Trabajemos Juntos?
          </h2>
          <p className="text-xl text-gray-300 mb-8 max-w-2xl mx-auto">
            Estoy disponible para nuevos proyectos y colaboraciones. ¡No dudes en contactarme!
          </p>
          <a href="mailto:contact@example.com" className="inline-block bg-gradient-to-r from-purple-600 to-pink-600 hover:from-purple-700 hover:to-pink-700 px-10 py-4 rounded-full text-lg font-semibold transition-all duration-300 hover:scale-105 shadow-lg">
            Enviar Mensaje
          </a>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-8 border-t border-purple-500/20">
        <div className="container mx-auto px-6 text-center text-gray-400">
          <p>© 2024 John Doe. Hecho con React y Tailwind CSS</p>
        </div>
      </footer>

      <style jsx>{`
        @keyframes float {
          0%, 100% { transform: translateY(0); }
          50% { transform: translateY(-20px); }
        }
        @keyframes fade-in {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        .animate-float {
          animation: float 3s ease-in-out infinite;
        }
        .animate-fade-in {
          animation: fade-in 1s ease-out;
        }
        .animate-fade-in-delay {
          animation: fade-in 1s ease-out 0.3s both;
        }
      `}</style>
    </div>
  );
}
