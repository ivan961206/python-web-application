import React, { useState } from 'react';

// Tailwind CSS is assumed to be available

// Main App Component
function App() {
  // Dummy data for available roosters
  const [roosters, setRoosters] = useState([
    {
      id: 1,
      name: 'El Rayo',
      image: 'https://placehold.co/400x300/e0e0e0/333333?text=Gallo+Ejemplo+1',
      cost: '1,500 MXN',
      owner: 'Juan Pérez',
      contact: 'info@ejemplo.com',
      description: 'Gallo joven con gran potencial, ideal para criadores que buscan mejorar su línea.',
    },
    {
      id: 2,
      name: 'El Huracán',
      image: 'https://placehold.co/400x300/e0e0e0/333333?text=Gallo+Ejemplo+2',
      cost: '2,200 MXN',
      owner: 'María García',
      contact: 'maria.g@ejemplo.com',
      description: 'Ejemplar con experiencia en torneos locales, temperamento fuerte y gran resistencia.',
    },
    {
      id: 3,
      name: 'El Centauro',
      image: 'https://placehold.co/400x300/e0e0e0/333333?text=Gallo+Ejemplo+3',
      cost: '1,800 MXN',
      owner: 'Rancho El Potrero',
      contact: 'ventas@potrero.com',
      description: 'Gallo de linaje puro, ideal para reproducción y mejora genética.',
    },
    {
      id: 4,
      name: 'El Gladiador',
      image: 'https://placehold.co/400x300/e0e0e0/333333?text=Gallo+Ejemplo+4',
      cost: '2,800 MXN',
      owner: 'Pedro Ramírez',
      contact: 'pedro.r@ejemplo.com',
      description: 'Gallo de gran tamaño y fuerza, con un historial de victorias impresionantes.',
    },
    {
      id: 5,
      name: 'La Furia Roja',
      image: 'https://placehold.co/400x300/e0e0e0/333333?text=Gallo+Ejemplo+5',
      cost: '1,950 MXN',
      owner: 'Ana Torres',
      contact: 'ana.t@ejemplo.com',
      description: 'Hembra de cría excepcional, ideal para fortalecer cualquier línea genética.',
    },
  ]);

  // Dummy data for Criaderos
  const [breeders, setBreeders] = useState([
    {
      id: 1,
      name: 'Rancho La Esperanza',
      image: 'https://placehold.co/400x250/004d40/ffffff?text=Rancho+La+Esperanza',
      description: 'Especialistas en líneas de combate de alta resistencia y velocidad. Compromiso con la genética y el bienestar animal.',
    },
    {
      id: 2,
      name: 'Hacienda El Poderoso',
      image: 'https://placehold.co/400x250/4a148c/ffffff?text=Hacienda+El+Poderoso',
      description: 'Reconocidos por sus gallos de gran envergadura y fuerza, con una trayectoria de campeones nacionales.',
    },
    {
      id: 3,
      name: 'Finca Los Invencibles',
      image: 'https://placehold.co/400x250/880e4f/ffffff?text=Finca+Los+Invencibles',
      description: 'Innovando en técnicas de crianza y entrenamiento, produciendo gallos ágiles y con gran temperamento.',
    },
  ]);

  // Dummy data for Tournaments
  const [tournaments, setTournaments] = useState([
    {
      id: 1,
      name: 'Gran Torneo Nacional de Campeones',
      date: '15-17 de Noviembre, 2025',
      location: 'Arena La Monumental, Ciudad de México',
      prizes: '$100,000 MXN y trofeo de oro',
      description: 'El evento más esperado del año, donde los mejores gallos del país se enfrentarán por la gloria.',
    },
    {
      id: 2,
      name: 'Copa Regional del Sureste',
      date: '2-3 de Diciembre, 2025',
      location: 'Palenque de Mérida, Yucatán',
      prizes: '$50,000 MXN y reconocimiento regional',
      description: 'Un torneo clave para descubrir nuevos talentos en la región sureste.',
    },
  ]);

  // Dummy data for Products
  const [products, setProducts] = useState([
    {
      id: 1,
      name: 'Alimento Premium para Gallos',
      image: 'https://placehold.co/200x200/d4af37/ffffff?text=Alimento+Premium',
      cost: '$350 MXN',
      description: 'Fórmula balanceada para fuerza y vitalidad.',
    },
    {
      id: 2,
      name: 'Vitaminas Esenciales',
      image: 'https://placehold.co/200x200/a8a29e/ffffff?text=Vitaminas+Esenciales',
      cost: '$180 MXN',
      description: 'Suplemento para mejorar el rendimiento.',
    },
    {
      id: 3,
      name: 'Equipo de Entrenamiento',
      image: 'https://placehold.co/200x200/94a3b8/ffffff?text=Equipo+de+Entrenamiento',
      cost: '$500 MXN',
      description: 'Jaulas y accesorios para preparación física.',
    },
    {
      id: 4,
      name: 'Guía de Crianza Avanzada',
      image: 'https://placehold.co/200x200/6b7280/ffffff?text=Libro+Crianza',
      cost: '$250 MXN',
      description: 'Consejos de expertos para criadores.',
    },
  ]);

  const [selectedRooster, setSelectedRooster] = useState(null);
  const [isModalOpen, setIsModalOpen] = useState(false);

  // Function to open the contact modal
  const openContactModal = (rooster) => {
    setSelectedRooster(rooster);
    setIsModalOpen(true);
  };

  // Function to close the contact modal
  const closeContactModal = () => {
    setIsModalOpen(false);
    setSelectedRooster(null);
  };

  return (
    <div className="min-h-screen bg-gray-100 font-anton text-uppercase">
      {/* Custom CSS for Anton and Great Vibes fonts */}
      <style>{`
        body {
            font-family: 'Anton', sans-serif;
            text-transform: uppercase;
        }
        .magazine-calligraphy {
            font-family: 'Great Vibes', cursive;
            text-transform: none;
            font-size: 1.8em;
            font-weight: normal;
            line-height: 1;
        }
        /* Ensure specific font-weight classes are reset as Anton is inherently bold */
        .font-semibold, .font-bold, .font-extrabold {
            font-weight: normal;
        }
        /* Common section title style */
        .section-title-app {
            position: relative;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
        .section-title-app::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 60px;
            height: 4px;
            background-color: #eab308; /* Amber accent color */
            border-radius: 9999px; /* Fully rounded */
        }
        /* Ensure navigation links stay on one line, potentially causing horizontal scroll on very small screens */
        .nav-links {
            white-space: nowrap; /* Prevent wrapping */
            overflow-x: auto; /* Allow horizontal scrolling if content overflows */
            -webkit-overflow-scrolling: touch; /* Smooth scrolling on iOS */
        }
        .nav-links::-webkit-scrollbar {
            display: none; /* Hide scrollbar for a cleaner look */
        }
      `}</style>

      {/* Header Section */}
      <header className="bg-black text-white shadow-lg py-4">
        <div className="container mx-auto flex flex-col md:flex-row justify-between items-center px-4">
          {/* Logo/Site Title with stacked "CASTA FINA" and "Magazine" */}
          <a href="#" className="flex flex-col items-center md:items-start text-amber-400 mb-4 md:mb-0 rounded-lg p-2 hover:text-amber-300 transition-colors">
            <span className="text-3xl">CASTA FINA</span>
            <span className="magazine-calligraphy text-2xl">Magazine</span>
          </a>
          {/* Navigation Menu (full menu for app context) */}
          <nav className="w-full md:w-auto">
            <ul className="flex justify-center md:justify-end space-x-4 md:space-x-6 nav-links">
              <li><a href="#gallo-semana" className="text-lg hover:text-amber-400 transition-colors rounded-md px-3 py-2">Gallo de la Semana</a></li>
              <li><a href="#criaderos" className="text-lg hover:text-amber-400 transition-colors rounded-md px-3 py-2">Criaderos</a></li>
              <li><a href="#torneos" className="text-lg hover:text-amber-400 transition-colors rounded-md px-3 py-2">Torneos</a></li>
              <li><a href="#productos" className="text-lg hover:text-amber-400 transition-colors rounded-md px-3 py-2">Productos</a></li>
              <li><a href="#gallos-disponibles" className="text-lg hover:text-amber-400 transition-colors rounded-md px-3 py-2">Gallos Disponibles</a></li>
            </ul>
          </nav>
        </div>
      </header>

      {/* Hero Section - App specific */}
      <section className="bg-gradient-to-r from-black to-gray-900 text-white py-20 text-center shadow-inner">
        <div className="container mx-auto px-4">
          <h1 className="text-5xl md:text-6xl mb-4 leading-tight">
            BIENVENIDOS A CASTA FINA MAGAZINE
          </h1>
          <p className="text-xl md:text-2xl mb-8 opacity-90">
            Tu fuente confiable de noticias, criaderos, torneos y los mejores ejemplares.
          </p>
          <a href="#gallo-semana" className="bg-amber-500 hover:bg-amber-600 text-gray-900 py-3 px-8 rounded-full text-lg shadow-lg transform hover:scale-105 transition-transform duration-300">
            Explora Ahora
          </a>
        </div>
      </section>

      {/* Mission Statement Section */}
      <section id="nuestra-vision" className="bg-amber-500 text-gray-900 py-12 text-center shadow-md">
        <div className="container mx-auto px-4">
          <h2 className="text-4xl mb-4">NUESTRA VISIÓN</h2>
          <p className="text-xl md:text-2xl max-w-3xl mx-auto leading-relaxed">
            En CASTA FINA MAGAZINE, estamos comprometidos con la preservación y el enaltecimiento de nuestras tradiciones gallísticas. Creemos firmemente que esta noble actividad es parte de nuestra cultura y queremos asegurar que siga viva para las futuras generaciones.
          </p>
        </div>
      </section>

      <main className="container mx-auto px-4 py-12">

        {/* Gallo de la Semana Section */}
        <section id="gallo-semana" className="mb-16 bg-white p-8 rounded-xl shadow-md">
          <h2 className="text-4xl text-gray-800 mb-6 section-title-app">Gallo de la Semana</h2>
          <div className="flex flex-col md:flex-row items-center md:space-x-8">
            <div className="md:w-1/2 mb-6 md:mb-0">
              <img src="https://placehold.co/600x400/b36b00/ffffff?text=Gallo+Destacado" alt="Gallo de la Semana" className="rounded-lg shadow-lg w-full h-auto object-cover" />
            </div>
            <div className="md:w-1/2">
              <h3 className="text-3xl text-amber-600 mb-3">"El Fénix" - Campeón Indiscutible</h3>
              <p className="text-gray-700 leading-relaxed mb-4">
                Conoce a "El Fénix", un ejemplar majestuoso que ha demostrado su valía en cada contienda. Su linaje se remonta a campeones legendarios, y su técnica en el ruedo es incomparable. Este gallo no solo es fuerte, sino también inteligente, capaz de adaptarse a cualquier oponente.
              </p>
              <p className="text-gray-600 text-sm">
                <em>Propietario: Rancho Las Palmas | Récord: 15-0 invicto</em>
              </p>
              <a href="#" className="inline-block mt-4 bg-black hover:bg-gray-900 text-white py-2 px-6 rounded-lg transition-colors">
                Leer Artículo Completo
              </a>
            </div>
          </div>
        </section>

        {/* Criaderos Section */}
        <section id="criaderos" className="mb-16 bg-white p-8 rounded-xl shadow-md">
          <h2 className="text-4xl text-gray-800 mb-6 section-title-app">Criaderos Destacados</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {breeders.map((breeder) => (
              <div key={breeder.id} className="bg-gray-50 p-6 rounded-lg shadow-sm border border-gray-200 hover:shadow-md transition-shadow">
                <img src={breeder.image} alt={breeder.name} className="rounded-md mb-4 w-full h-40 object-cover" />
                <h3 className="text-2xl text-gray-800 mb-2">{breeder.name}</h3>
                <p className="text-gray-600 mb-3">
                  {breeder.description}
                </p>
                <a href="#" className="text-amber-600 hover:text-amber-800">Ver Perfil</a>
              </div>
            ))}
          </div>
          <div className="text-center mt-8">
            <a href="#" className="inline-block bg-amber-500 hover:bg-amber-600 text-gray-900 py-3 px-8 rounded-full text-lg shadow-md transform hover:scale-105 transition-transform duration-300">
              Ver Todos los Criaderos
            </a>
          </div>
        </section>

        {/* Torneos Section */}
        <section id="torneos" className="mb-16 bg-white p-8 rounded-xl shadow-md">
          <h2 className="text-4xl text-gray-800 mb-6 section-title-app">Próximos Torneos</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {tournaments.map((tournament) => (
              <div key={tournament.id} className="bg-gray-50 p-6 rounded-lg shadow-sm border border-gray-200 hover:shadow-md transition-shadow">
                <h3 className="text-2xl text-gray-800 mb-2">{tournament.name}</h3>
                <p className="text-gray-600 mb-3">
                  <span className="font-normal">Fecha:</span> {tournament.date}<br />
                  <span className="font-normal">Lugar:</span> {tournament.location}<br />
                  <span className="font-normal">Premios:</span> {tournament.prizes}
                </p>
                <p className="text-gray-700 text-sm">
                  <em>{tournament.description}</em>
                </p>
                <a href="#" className="text-amber-600 hover:text-amber-800 mt-3 inline-block">Más Detalles</a>
              </div>
            ))}
          </div>
          <div className="text-center mt-8">
            <a href="#" className="inline-block bg-black hover:bg-gray-900 text-white py-3 px-8 rounded-full text-lg shadow-md transform hover:scale-105 transition-transform duration-300">
              Ver Calendario Completo
            </a>
          </div>
        </section>

        {/* Productos en Venta Section */}
        <section id="productos" className="mb-16 bg-white p-8 rounded-xl shadow-md">
          <h2 className="text-4xl text-gray-800 mb-6 section-title-app">Productos Esenciales</h2>
          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            {products.map((product) => (
              <div key={product.id} className="bg-gray-50 p-4 rounded-lg shadow-sm border border-gray-200 text-center hover:shadow-md transition-shadow">
                <img src={product.image} alt={product.name} className="rounded-md mb-4 mx-auto w-32 h-32 object-cover" />
                <h3 className="text-xl text-gray-800 mb-1">{product.name}</h3>
                <p className="text-amber-600 mb-2">{product.cost}</p>
                <p className="text-gray-600 text-sm mb-3">{product.description}</p>
                <button className="bg-amber-500 hover:bg-amber-600 text-gray-900 py-2 px-4 rounded-full text-sm">Añadir al Carrito</button>
              </div>
            ))}
          </div>
          <div className="text-center mt-8">
            <a href="#" className="inline-block bg-black hover:bg-gray-900 text-white py-3 px-8 rounded-full text-lg shadow-md transform hover:scale-105 transition-transform duration-300">
              Ver Catálogo Completo
            </a>
          </div>
        </section>

        {/* Gallos Disponibles Section */}
        <section id="gallos-disponibles" className="mb-16 bg-white p-8 rounded-xl shadow-md">
          <h2 className="text-4xl text-gray-800 mb-6 section-title-app">
            Explora Nuestra Selección de Gallos
          </h2>
          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
            {roosters.map((rooster) => (
              <RoosterCard key={rooster.id} rooster={rooster} onContactClick={openContactModal} />
            ))}
          </div>
        </section>
      </main>

      {/* Contact Modal */}
      {isModalOpen && selectedRooster && (
        <ContactModal rooster={selectedRooster} onClose={closeContactModal} />
      )}

      {/* Footer Section */}
      <footer className="bg-black text-white py-8">
        <div className="container mx-auto text-center px-4">
          <p className="mb-4">
            <a href="#" className="hover:text-amber-400 transition-colors mx-2">Acerca de Nosotros</a> |
            <a href="#" className="hover:text-amber-400 transition-colors mx-2">Política de Privacidad</a> |
            <a href="#" className="hover:text-amber-400 transition-colors mx-2">Términos y Condiciones</a> |
            <a href="#" className="hover:text-amber-400 transition-colors mx-2">Contacto</a>
          </p>
          <p className="mb-4">
            SÍGUENOS EN:
            <a href="https://www.facebook.com/CastaFina" target="_blank" className="hover:text-amber-400 transition-colors mx-2">FACEBOOK: CASTA FINA</a> |
            <a href="https://wa.me/5215613401049" target="_blank" className="hover:text-amber-400 transition-colors mx-2">WHATSAPP: 5613401049</a>
          </p>
          <p>&copy; 2025 CASTA FINA MAGAZINE. Todos los derechos reservados.</p>
        </div>
      </footer>
    </div>
  );
}

// Rooster Card Component (Remains the same)
const RoosterCard = ({ rooster, onContactClick }) => {
  return (
    <div className="bg-gray-50 p-6 rounded-lg shadow-sm border border-gray-200 flex flex-col items-center text-center hover:shadow-md transition-shadow">
      <img src={rooster.image} alt={rooster.name} className="rounded-md mb-4 w-full h-48 object-cover" />
      <h3 className="text-2xl text-gray-800 mb-2">{rooster.name}</h3>
      <p className="text-gray-600 mb-2">
        <span className="font-normal">Costo:</span> <span className="text-amber-600">{rooster.cost}</span><br />
        <span className="font-normal">Propietario:</span> {rooster.owner}
      </p>
      <p className="text-gray-700 text-sm mb-4">
        <em>{rooster.description}</em>
      </p>
      <button
        onClick={() => onContactClick(rooster)}
        className="mt-auto bg-amber-500 hover:bg-amber-600 text-gray-900 py-2 px-6 rounded-full text-sm shadow-md transition-colors"
      >
        CONTACTAR PROPIETARIO
      </button>
    </div>
  );
};

// Contact Modal Component (Remains the same)
const ContactModal = ({ rooster, onClose }) => {
  return (
    <div className="fixed inset-0 bg-black bg-opacity-75 flex items-center justify-center p-4 z-50">
      <div className="bg-white p-8 rounded-lg shadow-xl max-w-md w-full relative">
        <button
          onClick={onClose}
          className="absolute top-4 right-4 text-gray-600 hover:text-gray-900 text-2xl"
        >
          &times;
        </button>
        <h2 className="text-3xl text-gray-800 mb-4 font-anton">CONTACTO PARA {rooster.name}</h2>
        <p className="text-gray-700 mb-2">
          <span className="font-normal">Propietario:</span> {rooster.owner}
        </p>
        <p className="text-gray-700 mb-4">
          <span className="font-normal">Email:</span> <a href={`mailto:${rooster.contact}`} className="text-amber-600 hover:underline">{rooster.contact}</a>
        </p>
        <p className="text-gray-600 text-sm">
          Por favor, envía un correo electrónico al propietario para más detalles.
        </p>
        <button
          onClick={onClose}
          className="mt-6 bg-amber-500 hover:bg-amber-600 text-gray-900 py-2 px-6 rounded-full text-lg shadow-md transition-colors"
        >
          CERRAR
        </button>
      </div>
    </div>
  );
};

export default App;

