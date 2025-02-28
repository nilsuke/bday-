/** @jsxImportSource https://esm.sh/react@18.2.0 */
import { createRoot } from "https://esm.sh/react-dom@18.2.0/client";
import React, { useEffect, useState } from "https://esm.sh/react@18.2.0";

function BirthdayCard() {
  const [showPoem, setShowPoem] = useState(false);
  const [candles, setCandles] = useState(Array(10).fill(false));
  const [isMobile, setIsMobile] = useState(false);

  useEffect(() => {
    const checkMobile = () => {
      setIsMobile(window.innerWidth <= 768);
    };
    
    checkMobile();
    window.addEventListener('resize', checkMobile);
    return () => window.removeEventListener('resize', checkMobile);
  }, []);

  const poem = `
    Dearest Sam, on this special day,
    Your light shines bright in every way.
    Another year of joy and grace,
    A smile that lights up every place.

    Laughter, love, and dreams so grand,
    Your spirit sparkles, simply planned.
    May this birthday bring you cheer,
    Celebrating the wonderful you we hold dear! 🎂🎈
  `;

  useEffect(() => {
    if (showPoem) {
      const candleTimer = setTimeout(() => {
        setCandles(candles.map(() => true));
      }, 500);
      return () => clearTimeout(candleTimer);
    }
  }, [showPoem]);

  const AnimatedTitle = () => {
    const words = ["Happy", "Birthday", "Sam!"];

    return (
      <div
        style={{
          display: "flex",
          flexDirection: isMobile ? "column" : "row",
          justifyContent: "center",
          alignItems: "center",
          gap: isMobile ? "10px" : "15px",
          perspective: "1000px",
          textAlign: "center",
        }}
      >
        {words.map((word, index) => (
          <h1
            key={word}
            style={{
              fontSize: isMobile ? "2.5rem" : "4rem",
              fontWeight: "900",
              color: "#FFFFFF",
              textShadow: "3px 3px 6px rgba(0,0,0,0.3)",
              background: "linear-gradient(45deg, #FF69B4, #FF1493)",
              WebkitBackgroundClip: "text",
              WebkitTextFillColor: "transparent",
              animation: `wordAnimation 1s ease-in-out ${index * 0.3}s forwards`,
              opacity: 0,
              transform: "rotateX(90deg)",
              display: "inline-block",
              transformOrigin: "center bottom",
              margin: 0,
            }}
          >
            {word}
          </h1>
        ))}
      </div>
    );
  };

  const Candle = ({ lit }) => (
    <div
      style={{
        width: isMobile ? "20px" : "30px",
        height: isMobile ? "80px" : "100px",
        backgroundColor: lit ? "#FF6B6B" : "#E0E0E0",
        margin: "0 5px",
        borderRadius: "10px",
        position: "relative",
        transition: "all 0.5s ease",
      }}
    >
      {lit && (
        <div
          style={{
            position: "absolute",
            top: "-15px",
            left: "50%",
            transform: "translateX(-50%)",
            width: "8px",
            height: "25px",
            backgroundColor: "#FFD700",
            borderRadius: "50%",
            animation: "flicker 1s infinite alternate",
          }}
        />
      )}
    </div>
  );

  const BirthdayCake = () => (
    <div
      style={{
        display: "flex",
        flexDirection: "column",
        alignItems: "center",
        marginTop: "20px",
      }}
    >
      <div
        style={{
          width: isMobile ? "250px" : "300px",
          height: isMobile ? "120px" : "150px",
          backgroundColor: "#FFC0CB",
          borderRadius: "10px",
          display: "flex",
          justifyContent: "center",
          alignItems: "flex-end",
          padding: "20px",
          boxShadow: "0 10px 20px rgba(0,0,0,0.1)",
        }}
      >
        <div
          style={{
            display: "flex",
            justifyContent: "center",
            marginBottom: "10px",
          }}
        >
          {candles.map((lit, index) => <Candle key={index} lit={lit} />)}
        </div>
      </div>
    </div>
  );

  const BirthdayConfetti = () => {
    return Array(50).fill(0).map((_, index) => {
      const colors = ["#FF69B4", "#FFB6C1", "#FF1493", "#FFC0CB", "#FF85A2"];
      const style = {
        position: "absolute",
        width: `${Math.random() * 10 + 5}px`,
        height: `${Math.random() * 10 + 5}px`,
        backgroundColor: colors[Math.floor(Math.random() * colors.length)],
        borderRadius: "50%",
        top: `${Math.random() * 100}%`,
        left: `${Math.random() * 100}%`,
        animation: `float ${Math.random() * 3 + 2}s ease-in-out infinite`,
        opacity: Math.random(),
        transform: `rotate(${Math.random() * 360}deg)`,
        display: isMobile ? "none" : "block",  // Hide on mobile to improve performance
      };
      return <div key={index} style={style} />;
    });
  };

  const BalloonDecoration = () => {
    return Array(10).fill(0).map((_, index) => {
      const colors = ["#FF69B4", "#FF1493", "#FFB6C1", "#FF85A2"];
      const style = {
        position: "absolute",
        width: `${Math.random() * 50 + 30}px`,
        height: `${Math.random() * 80 + 50}px`,
        backgroundColor: colors[Math.floor(Math.random() * colors.length)],
        borderRadius: "50% 50% 50% 50% / 60% 60% 40% 40%",
        top: `${Math.random() * 100}%`,
        left: `${Math.random() * 100}%`,
        opacity: 0.7,
        animation: `float ${Math.random() * 5 + 3}s ease-in-out infinite`,
        transformOrigin: "bottom center",
        zIndex: -1,
        display: isMobile ? "none" : "block",  // Hide on mobile to improve performance
      };
      return <div key={index} style={style} />;
    });
  };

  return (
    <div
      style={{
        fontFamily: "Arial, sans-serif",
        minHeight: "100vh",
        display: "flex",
        flexDirection: "column",
        justifyContent: "center",
        alignItems: "center",
        background: !showPoem 
          ? "linear-gradient(135deg, #FFB6C1, #FFC0CB, #FFE4E1)" 
          : "linear-gradient(135deg, #87CEEB, #B0E0E6, #4682B4)",
        textAlign: "center",
        padding: isMobile ? "10px" : "20px",
        color: "white",
        overflow: "hidden",
        position: "relative",
      }}
    >
      <style>
        {`
        @keyframes flicker {
          0% { opacity: 0.8; }
          100% { opacity: 1; }
        }
        @keyframes float {
          0%, 100% { transform: translateY(0); }
          50% { transform: translateY(-20px); }
        }
        @keyframes wordAnimation {
          0% { 
            opacity: 0;
            transform: rotateX(90deg);
          }
          70% {
            transform: rotateX(-10deg);
          }
          100% { 
            opacity: 1;
            transform: rotateX(0deg);
          }
        }
        @media (max-width: 768px) {
          body {
            overflow-x: hidden;
          }
        }
      `}
      </style>
      <BirthdayConfetti />
      <BalloonDecoration />
      {!showPoem
        ? (
          <>
            <AnimatedTitle />
            <div
              style={{
                display: "flex",
                flexDirection: isMobile ? "column" : "row",
                gap: isMobile ? "15px" : "20px",
                marginTop: "30px",
                zIndex: 10,
                position: "relative",
                alignItems: "center",
              }}
            >
              <button
                onClick={() => setShowPoem(true)}
                style={{
                  padding: isMobile ? "12px 20px" : "15px 30px",
                  backgroundColor: "white",
                  color: "#FF1493",
                  border: "3px solid #FF1493",
                  borderRadius: "15px",
                  cursor: "pointer",
                  fontSize: isMobile ? "1rem" : "1.3rem",
                  boxShadow: "0 6px 12px rgba(255,20,147,0.4)",
                  transition: "all 0.3s ease",
                  transform: "perspective(200px) rotateX(10deg)",
                  fontWeight: "bold",
                  width: isMobile ? "100%" : "auto",
                }}
                onMouseOver={(e) => {
                  e.target.style.transform = "perspective(200px) rotateX(0deg)";
                  e.target.style.boxShadow = "0 10px 20px rgba(255,20,147,0.6)";
                }}
                onMouseOut={(e) => {
                  e.target.style.transform = "perspective(200px) rotateX(10deg)";
                  e.target.style.boxShadow = "0 6px 12px rgba(255,20,147,0.4)";
                }}
              >
                Click Here for Surprise 🎁
              </button>
            </div>
          </>
        )
        : (
          <div
            style={{
              backgroundColor: "rgba(255,255,255,0.9)",
              padding: isMobile ? "15px" : "30px",
              borderRadius: "15px",
              width: isMobile ? "90%" : "600px",
              maxWidth: "600px",
              boxShadow: "0 15px 30px rgba(0,0,0,0.3)",
              position: "relative",
              overflow: "hidden",
            }}
          >
            <BirthdayCake />
            <h2
              style={{
                color: "#4682B4",
                fontFamily: "Pacifico, cursive",
                fontSize: isMobile ? "2rem" : "2.5rem",
                textShadow: "2px 2px 4px rgba(0,0,0,0.2)",
              }}
            >
             Poem For Sam
            </h2>
            <pre
              style={{
                whiteSpace: "pre-wrap",
                fontFamily: "Georgia, serif",
                lineHeight: "1.6",
                color: "#333",
                fontSize: isMobile ? "1rem" : "1.2rem",
                overflowWrap: "break-word",
                wordWrap: "break-word",
              }}
            >
            {poem}
            </pre>
            <button
              onClick={() => setShowPoem(false)}
              style={{
                marginTop: "20px",
                padding: isMobile ? "10px 20px" : "12px 25px",
                backgroundColor: "#4682B4",
                color: "white",
                border: "none",
                borderRadius: "10px",
                cursor: "pointer",
                transition: "all 0.3s ease",
                fontSize: isMobile ? "0.9rem" : "1rem",
                width: isMobile ? "100%" : "auto",
              }}
              onMouseOver={(e) => {
                e.target.style.transform = "scale(1.05)";
                e.target.style.boxShadow = "0 6px 12px rgba(70,130,180,0.4)";
              }}
              onMouseOut={(e) => {
                e.target.style.transform = "scale(1)";
                e.target.style.boxShadow = "none";
              }}
            >
              Back to Greeting 🎈
            </button>
          </div>
        )}
    </div>
  );
}

function client() {
  createRoot(document.getElementById("root")).render(<BirthdayCard />);
}

if (typeof document !== "undefined") { client(); }

export default async function server(request: Request): Promise<Response> {
  return new Response(
    `
    <html>
      <head>
        <title>Happy Birthday Sam!</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
        <link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
        <style>
          body { 
            margin: 0; 
            overflow-x: hidden;
            touch-action: manipulation;
          }
        </style>
      </head>
      <body>
        <div id="root"></div>
        <script src="https://esm.town/v/std/catch"></script>
        <script type="module" src="${import.meta.url}"></script>
      </body>
    </html>
  `,
    {
      headers: { "content-type": "text/html" },
    },
  );
}
