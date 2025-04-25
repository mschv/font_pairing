import React, { useState, useEffect } from 'react';

const SimplifiedFontPairingWidget = () => {
  const fontSize = { heading: 32, body: 16 };
  
  // Available heading fonts
  const headingFonts = [
    "Playfair Display",
    "Montserrat", 
    "Oswald",
    "Lora",
    "Raleway",
    "Libre Baskerville",
    "Poppins",
    "Abril Fatface",
    "Quicksand"
  ];
  
  // Available vibes/styles
  const vibes = [
    "Professional",
    "Creative",
    "Elegant",
    "Modern",
    "Bold"
  ];
  
  // Body font options for each heading + vibe combination
  const bodyFontOptions = {
    "Playfair Display": {
      "Professional": ["Source Sans Pro", "Roboto", "IBM Plex Sans"],
      "Creative": ["Nunito", "Lato", "Montserrat"],
      "Elegant": ["Lato", "Cormorant Garamond", "Merriweather"],
      "Modern": ["Work Sans", "Open Sans", "Inter"],
      "Bold": ["Open Sans", "Source Sans Pro", "Raleway"]
    },
    "Montserrat": {
      "Professional": ["Roboto", "Source Sans Pro", "IBM Plex Sans"],
      "Creative": ["Lora", "Nunito", "Playfair Display"],
      "Elegant": ["Merriweather", "Libre Baskerville", "Lora"],
      "Modern": ["Open Sans", "Work Sans", "Inter"],
      "Bold": ["Source Sans Pro", "Raleway", "Roboto"]
    },
    "Oswald": {
      "Professional": ["Roboto", "Source Sans Pro", "Open Sans"],
      "Creative": ["Lato", "Nunito", "Montserrat"],
      "Elegant": ["Merriweather", "Libre Baskerville", "Lora"],
      "Modern": ["Open Sans", "Work Sans", "Inter"],
      "Bold": ["Source Sans Pro", "Roboto", "Nunito Sans"]
    },
    "Lora": {
      "Professional": ["Roboto Slab", "Source Sans Pro", "Open Sans"],
      "Creative": ["Montserrat", "Nunito", "Quicksand"],
      "Elegant": ["Open Sans", "Cormorant Garamond", "Lato"],
      "Modern": ["Work Sans", "IBM Plex Sans", "Inter"],
      "Bold": ["Raleway", "Montserrat", "Source Sans Pro"]
    },
    "Raleway": {
      "Professional": ["IBM Plex Sans", "Source Sans Pro", "Open Sans"],
      "Creative": ["Nunito", "Montserrat", "Quicksand"],
      "Elegant": ["Lora", "Playfair Display", "Libre Baskerville"],
      "Modern": ["Open Sans", "Work Sans", "Inter"],
      "Bold": ["Poppins", "Montserrat", "Oswald"]
    },
    "Libre Baskerville": {
      "Professional": ["Work Sans", "IBM Plex Sans", "Source Sans Pro"],
      "Creative": ["Montserrat", "Raleway", "Nunito"],
      "Elegant": ["Source Sans Pro", "Open Sans", "Lato"],
      "Modern": ["Open Sans", "Work Sans", "Roboto"],
      "Bold": ["Roboto", "Montserrat", "Oswald"]
    },
    "Poppins": {
      "Professional": ["Nunito Sans", "Source Sans Pro", "Open Sans"],
      "Creative": ["Lora", "Playfair Display", "Nunito"],
      "Elegant": ["Playfair Display", "Cormorant Garamond", "Libre Baskerville"],
      "Modern": ["Work Sans", "IBM Plex Sans", "Inter"],
      "Bold": ["Oswald", "Montserrat", "Roboto"]
    },
    "Abril Fatface": {
      "Professional": ["Roboto", "Source Sans Pro", "Open Sans"],
      "Creative": ["Lato", "Nunito", "Montserrat"],
      "Elegant": ["Merriweather", "Libre Baskerville", "Playfair Display"],
      "Modern": ["Work Sans", "IBM Plex Sans", "Inter"],
      "Bold": ["Oswald", "Montserrat", "Open Sans"]
    },
    "Quicksand": {
      "Professional": ["Roboto", "IBM Plex Sans", "Source Sans Pro"],
      "Creative": ["Nunito", "Montserrat", "Lato"],
      "Elegant": ["Playfair Display", "Lora", "Libre Baskerville"],
      "Modern": ["Open Sans", "Work Sans", "Inter"],
      "Bold": ["Oswald", "Poppins", "Montserrat"]
    }
  };

  // State for selected fonts and vibe
  const [selectedHeading, setSelectedHeading] = useState(headingFonts[0]);
  const [selectedVibe, setSelectedVibe] = useState(vibes[0]);
  const [selectedBodyFont, setSelectedBodyFont] = useState("");
  const [showTips, setShowTips] = useState(false);
  const [copied, setCopied] = useState(false);
  const [previewVisible, setPreviewVisible] = useState(true);
  
  // Update body font when heading or vibe changes
  useEffect(() => {
    setSelectedBodyFont(bodyFontOptions[selectedHeading][selectedVibe][0]);
  }, [selectedHeading, selectedVibe]);

  // Function to copy font pairing info to clipboard
  const copyFontPairing = () => {
    setCopied(true);
    setTimeout(() => setCopied(false), 2000);
  };

  const vibeDescriptions = {
    "Professional": "Clean and formal style suitable for business documents and corporate websites.",
    "Creative": "Expressive style that adds personality to blogs and artistic projects.",
    "Elegant": "Refined style perfect for invitations, luxury brands, and formal announcements.",
    "Modern": "Contemporary look with clean lines ideal for tech startups and minimalist designs.",
    "Bold": "Strong visual impact for headlines, advertisements, and attention-grabbing content."
  };

  return (
    <div className="font-sans p-6 max-w-4xl mx-auto bg-gray-50 rounded-lg">
      {/* Header with Notion-like styling */}
      <div className="mb-8 text-center">
        <h1 className="text-3xl font-bold text-gray-800 mb-2">Font Pairing Explorer</h1>
        <p className="text-gray-500 text-sm">Find beautiful font combinations for your next project</p>
      </div>
      
      {/* Main content area */}
      <div className="bg-white rounded-lg shadow-sm border border-gray-200 p-6 mb-6">
        {/* Selection area */}
        <div className="mb-8">
          <div className="flex items-center mb-2">
            <div className="w-3 h-3 rounded-full bg-blue-400 mr-2"></div>
            <h2 className="text-sm font-medium text-gray-700">Select Your Font Pairing</h2>
          </div>

          {/* Step 1: Choose a vibe */}
          <div className="mb-6">
            <label className="block text-sm font-medium text-gray-700 mb-2">1. Choose a vibe</label>
            <div className="flex flex-wrap gap-2">
              {vibes.map(vibe => (
                <button
                  key={vibe}
                  onClick={() => setSelectedVibe(vibe)}
                  className={`px-3 py-1.5 text-sm rounded-md transition-all ${
                    selectedVibe === vibe 
                    ? 'bg-blue-50 text-blue-700 border border-blue-200' 
                    : 'bg-gray-50 text-gray-700 border border-gray-200 hover:bg-gray-100'
                  }`}
                >
                  {vibe}
                </button>
              ))}
            </div>
            <p className="text-xs text-gray-500 mt-2 italic">{vibeDescriptions[selectedVibe]}</p>
          </div>

          {/* Step 2: Choose heading and body fonts */}
          <div className="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
            {/* Heading font dropdown */}
            <div>
              <label className="block text-sm font-medium text-gray-700 mb-2">2. Select heading font</label>
              <div className="relative">
                <select 
                  value={selectedHeading}
                  onChange={(e) => setSelectedHeading(e.target.value)}
                  className="block w-full pl-3 pr-10 py-2 text-base border border-gray-300 focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm rounded-md"
                  style={{ fontFamily: `"${selectedHeading}", serif` }}
                >
                  {headingFonts.map(font => (
                    <option key={font} value={font} style={{ fontFamily: `"${font}", serif` }}>
                      {font}
                    </option>
                  ))}
                </select>
                <div className="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
                  <svg className="h-4 w-4" fill="currentColor" viewBox="0 0 20 20">
                    <path fillRule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clipRule="evenodd"></path>
                  </svg>
                </div>
              </div>
            </div>

            {/* Body font dropdown */}
            <div>
              <label className="block text-sm font-medium text-gray-700 mb-2">3. Select body font</label>
              <div className="relative">
                <select 
                  value={selectedBodyFont}
                  onChange={(e) => setSelectedBodyFont(e.target.value)}
                  className="block w-full pl-3 pr-10 py-2 text-base border border-gray-300 focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm rounded-md"
                  style={{ fontFamily: `"${selectedBodyFont}", sans-serif` }}
                >
                  {bodyFontOptions[selectedHeading][selectedVibe].map(font => (
                    <option key={font} value={font} style={{ fontFamily: `"${font}", sans-serif` }}>
                      {font}
                    </option>
                  ))}
                </select>
                <div className="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
                  <svg className="h-4 w-4" fill="currentColor" viewBox="0 0 20 20">
                    <path fillRule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clipRule="evenodd"></path>
                  </svg>
                </div>
              </div>
            </div>
          </div>

          {/* Actions */}
          <div className="flex justify-between">
            <button 
              onClick={() => setShowTips(!showTips)} 
              className="text-gray-500 hover:text-gray-700 text-sm flex items-center gap-1 px-3 py-1.5 rounded hover:bg-gray-100"
            >
              <svg xmlns="http://www.w3.org/2000/svg" className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              Typography Tips
            </button>
            
            <div className="flex gap-2">
              <button 
                onClick={copyFontPairing} 
                className="text-gray-500 hover:text-gray-700 text-sm flex items-center gap-1 px-3 py-1.5 rounded hover:bg-gray-100"
              >
                <svg xmlns="http://www.w3.org/2000/svg" className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z" />
                </svg>
                {copied ? "Copied!" : "Copy Pairing"}
              </button>
              
              <button 
                onClick={() => setPreviewVisible(!previewVisible)} 
                className="bg-blue-500 hover:bg-blue-600 text-white text-sm px-4 py-1.5 rounded transition-colors"
              >
                {previewVisible ? "Hide Preview" : "Show Preview"}
              </button>
            </div>
          </div>
        </div>
        
        {/* Tips panel */}
        {showTips && (
          <div className="bg-gray-50 p-4 rounded-md mb-6 border border-gray-200">
            <div className="flex items-center justify-between mb-2">
              <h3 className="text-sm font-medium text-gray-700">Typography Tips</h3>
              <button onClick={() => setShowTips(false)} className="text-gray-400 hover:text-gray-700">
                <svg xmlns="http://www.w3.org/2000/svg" className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
            </div>
            <ul className="text-gray-600 text-xs space-y-1.5">
              <li className="flex items-start">
                <span className="inline-block w-4 text-gray-400 mr-1">•</span>
                <span><strong>Professional</strong>: Sans-serif headings with clean body fonts create a business-ready look</span>
              </li>
              <li className="flex items-start">
                <span className="inline-block w-4 text-gray-400 mr-1">•</span>
                <span><strong>Creative</strong>: Mix display fonts with readable body text for artistic expression</span>
              </li>
              <li className="flex items-start">
                <span className="inline-block w-4 text-gray-400 mr-1">•</span>
                <span><strong>Elegant</strong>: Serif fonts add sophistication and timeless appeal</span>
              </li>
              <li className="flex items-start">
                <span className="inline-block w-4 text-gray-400 mr-1">•</span>
                <span><strong>Modern</strong>: Geometric sans-serifs with minimal styling feel contemporary</span>
              </li>
              <li className="flex items-start">
                <span className="inline-block w-4 text-gray-400 mr-1">•</span>
                <span><strong>Bold</strong>: Strong weight contrasts create impactful visual hierarchy</span>
              </li>
            </ul>
          </div>
        )}
        
        {/* Preview Section */}
        {previewVisible && (
          <div className="mb-2">
            <div className="flex items-center mb-4">
              <div className="w-3 h-3 rounded-full bg-green-400 mr-2"></div>
              <h2 className="text-sm font-medium text-gray-700">Preview</h2>
            </div>
            
            <div className="bg-white rounded-lg p-6 border border-gray-200">
              <div className="flex items-center justify-between mb-4">
                <div className="flex items-center">
                  <div className="h-3 w-3 rounded-full bg-red-400 mr-1.5"></div>
                  <div className="h-3 w-3 rounded-full bg-yellow-400 mr-1.5"></div>
                  <div className="h-3 w-3 rounded-full bg-green-400"></div>
                </div>
                <div className="text-xs text-gray-400">{selectedHeading} + {selectedBodyFont}</div>
              </div>
              
              <h2 
                style={{
                  fontFamily: `"${selectedHeading}", serif`,
                  fontSize: `${fontSize.heading}px`,
                  fontWeight: "700",
                  lineHeight: "1.2"
                }}
                className="mb-4"
              >
                This is a heading in {selectedHeading}
              </h2>
              <p 
                style={{
                  fontFamily: `"${selectedBodyFont}", sans-serif`,
                  fontSize: `${fontSize.body}px`,
                  lineHeight: "1.6"
                }}
                className="text-gray-700"
              >
                This is body text in {selectedBodyFont}. Great typography improves readability, 
                establishes hierarchy, and enhances the user experience. This {selectedVibe.toLowerCase()} 
                pairing creates a visual harmony that guides readers through your content effectively 
                while maintaining your brand's personality.
              </p>
            </div>
        
      </div>
      
      {/* Footer */}
      <div className="mt-6 text-center text-xs text-gray-400">
        <p>Font Pairing Explorer • Inspired by Notion</p>
      </div>
    </div>
  );
};

export default SimplifiedFontPairingWidget;
