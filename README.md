import React, { useState } from 'react';
import { 
  Linkedin, 
  Mail, 
  WhatsApp, 
  Github, 
  Code, 
  Database, 
  Server, 
  BookOpen,
  FileCode 
} from 'lucide-react';

const HenryAntwi = () => {
  const [activeSection, setActiveSection] = useState('skills');

  const skills = [
    { name: 'Python', icon: <Code color="#3776AB" />, proficiency: 90 },
    { name: 'Django', icon: <Server color="#092E20" />, proficiency: 85 },
    { name: 'Node.js', icon: <FileCode color="#339933" />, proficiency: 80 },
    { name: 'Express.js', icon: <Server color="#000000" />, proficiency: 75 },
    { name: 'FastAPI', icon: <Server color="#009688" />, proficiency: 80 },
    { name: 'PostgreSQL', icon: <Database color="#336791" />, proficiency: 75 },
    { name: 'Motoko', icon: <Code color="#6E4A7C" />, proficiency: 70 }
  ];

  const projects = [
    {
      name: 'AI Data Pipeline',
      description: 'Developed a scalable data processing system using Django and Machine Learning',
      technologies: ['Python', 'Django', 'ML']
    },
    {
      name: 'RESTful API Platform',
      description: 'Created comprehensive backend services with Express.js and PostgreSQL',
      technologies: ['Node.js', 'Express', 'PostgreSQL', 'Docker']
    },
    {
      name: 'Blockchain Dapp',
      description: 'Developed a decentralized application using Motoko on the Internet Computer',
      technologies: ['Motoko', 'Internet Computer', 'Blockchain']
    }
  ];

  return (
    <div className="max-w-4xl mx-auto p-6 bg-gray-50 rounded-xl shadow-lg">
      <div className="text-center mb-8">
        <h1 className="text-4xl font-bold text-gray-800 mb-2">
          Henry Nana Antwi
        </h1>
        <p className="text-xl text-gray-600">
          Full Stack Developer | Backend & Blockchain Enthusiast
        </p>
      </div>

      <div className="flex justify-center space-x-4 mb-8">
        <a 
          href="https://www.linkedin.com/in/henry-antwi-891906202/" 
          target="_blank" 
          className="hover:scale-110 transition-transform"
        >
          <Linkedin size={32} className="text-blue-600" />
        </a>
        <a 
          href="mailto:antwi.henry@outlook.com" 
          className="hover:scale-110 transition-transform"
        >
          <Mail size={32} className="text-red-500" />
        </a>
        <a 
          href="https://wa.me/233200570130" 
          target="_blank" 
          className="hover:scale-110 transition-transform"
        >
          <WhatsApp size={32} className="text-green-500" />
        </a>
        <a 
          href="https://github.com/henryantwi" 
          target="_blank" 
          className="hover:scale-110 transition-transform"
        >
          <Github size={32} className="text-gray-800" />
        </a>
      </div>

      <div className="bg-white rounded-lg shadow-md p-6">
        <div className="flex mb-4 border-b">
          {['skills', 'projects'].map(section => (
            <button
              key={section}
              onClick={() => setActiveSection(section)}
              className={`px-4 py-2 ${
                activeSection === section 
                  ? 'border-b-2 border-blue-500 text-blue-600' 
                  : 'text-gray-500'
              } uppercase tracking-wider`}
            >
              {section}
            </button>
          ))}
        </div>

        {activeSection === 'skills' && (
          <div className="grid grid-cols-2 gap-4">
            {skills.map(skill => (
              <div 
                key={skill.name} 
                className="flex items-center space-x-3 bg-gray-100 p-3 rounded-lg"
              >
                {skill.icon}
                <div className="flex-grow">
                  <div className="flex justify-between mb-1">
                    <span className="text-sm font-medium">{skill.name}</span>
                    <span className="text-sm">{skill.proficiency}%</span>
                  </div>
                  <div className="w-full bg-gray-200 rounded-full h-2.5">
                    <div 
                      className="bg-blue-600 h-2.5 rounded-full" 
                      style={{width: `${skill.proficiency}%`}}
                    ></div>
                  </div>
                </div>
              </div>
            ))}
          </div>
        )}

        {activeSection === 'projects' && (
          <div className="space-y-4">
            {projects.map(project => (
              <div 
                key={project.name} 
                className="border-l-4 border-blue-500 pl-4 py-2 bg-gray-50"
              >
                <h3 className="text-lg font-semibold text-gray-800">
                  {project.name}
                </h3>
                <p className="text-gray-600">{project.description}</p>
                <div className="flex space-x-2 mt-2">
                  {project.technologies.map(tech => (
                    <span 
                      key={tech} 
                      className="px-2 py-1 bg-blue-100 text-blue-800 rounded-full text-xs"
                    >
                      {tech}
                    </span>
                  ))}
                </div>
              </div>
            ))}
          </div>
        )}
      </div>

      <div className="mt-8 text-center">
        <img 
          src="https://streak-stats.demolab.com/?user=henryantwi&theme=dark&hide_border=true&date_format=M%20j%5B%2C%20Y%5D" 
          alt="GitHub Streak" 
          className="mx-auto"
        />
      </div>
    </div>
  );
};

export default HenryAntwi;
