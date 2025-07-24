import { MovieCard } from "@/components/MovieCard";
import { QRCodeGenerator } from "@/components/QRCodeGenerator";
import { Button } from "@/components/ui/button";
import { Badge } from "@/components/ui/badge";
import { Film, User, Star, Sparkles } from "lucide-react";
import { Link } from "react-router-dom";
import cosmicJourney from "@/assets/cosmic-journey.jpg";
import midnightShadows from "@/assets/midnight-shadows.jpg";
import oceansDream from "@/assets/oceans-dream.jpg";

const Index = () => {
  const featuredMovies = [
    {
      title: "Cosmic Journey",
      poster: cosmicJourney,
      rating: 8.7,
      genre: "Sci-Fi",
      year: 2024,
      description: "An epic space adventure that takes viewers on a breathtaking journey through distant galaxies. With stunning visuals and a compelling story about humanity's place in the universe.",
      reviews: [
        { author: "Alex Chen", comment: "Visually stunning and emotionally powerful!", rating: 9 },
        { author: "Maria Rodriguez", comment: "A masterpiece of modern sci-fi cinema.", rating: 8 }
      ]
    },
    {
      title: "Midnight Shadows",
      poster: midnightShadows,
      rating: 7.9,
      genre: "Thriller",
      year: 2024,
      description: "A gripping noir thriller set in the dark alleys of a metropolitan city. Detective Sarah Mills must solve a series of mysterious cases that lead to a shocking revelation.",
      reviews: [
        { author: "David Kim", comment: "Edge-of-your-seat suspense throughout!", rating: 8 },
        { author: "Emily Johnson", comment: "Classic noir with a modern twist.", rating: 7 }
      ]
    },
    {
      title: "Ocean's Dream",
      poster: oceansDream,
      rating: 8.2,
      genre: "Adventure",
      year: 2024,
      description: "Dive into an underwater adventure filled with wonder and discovery. A marine biologist uncovers ancient secrets hidden in the depths of the ocean.",
      reviews: [
        { author: "Sophie Wilson", comment: "Beautiful underwater cinematography!", rating: 9 },
        { author: "Michael Brown", comment: "A family-friendly adventure with heart.", rating: 8 }
      ]
    }
  ];

  return (
    <div className="min-h-screen bg-background bg-gradient-hero">
      {/* Header */}
      <header className="border-b border-border/30 bg-card/20 backdrop-blur-md sticky top-0 z-50">
        <div className="container mx-auto px-4 py-4">
          <nav className="flex items-center justify-between">
            <div className="flex items-center gap-3">
              <div className="w-10 h-10 bg-primary/20 rounded-full flex items-center justify-center">
                <Film className="w-6 h-6 text-primary" />
              </div>
              <h1 className="text-2xl font-bold text-foreground">FlickScan</h1>
            </div>
            <div className="flex items-center gap-4">
              <Badge variant="outline" className="border-accent/30 text-accent bg-accent/10">
                <Sparkles className="w-3 h-3 mr-1" />
                Latest Reviews
              </Badge>
              <Link to="/login">
                <Button variant="cinema" size="sm">
                  <User className="w-4 h-4" />
                  Sign In
                </Button>
              </Link>
            </div>
          </nav>
        </div>
      </header>

      {/* Hero Section */}
      <section className="py-16">
        <div className="container mx-auto px-4 text-center">
          <h2 className="text-5xl font-bold text-foreground mb-6">
            Discover Amazing
            <span className="text-primary block">Movie Reviews</span>
          </h2>
          <p className="text-xl text-muted-foreground mb-8 max-w-2xl mx-auto">
            Explore in-depth reviews, ratings, and insights from movie enthusiasts. 
            Find your next favorite film with FlickScan.
          </p>
          <div className="flex items-center justify-center gap-4 mb-8">
            <div className="flex items-center gap-2 bg-card/30 px-4 py-2 rounded-full border border-border/30">
              <Star className="w-4 h-4 text-primary fill-primary" />
              <span className="text-foreground font-medium">4.8/5 Average Rating</span>
            </div>
            <div className="flex items-center gap-2 bg-card/30 px-4 py-2 rounded-full border border-border/30">
              <Film className="w-4 h-4 text-accent" />
              <span className="text-foreground font-medium">500+ Movies Reviewed</span>
            </div>
          </div>
        </div>
      </section>

      {/* Featured Movies */}
      <section className="py-16">
        <div className="container mx-auto px-4">
          <h3 className="text-3xl font-bold text-foreground mb-8 text-center">
            Featured Reviews
          </h3>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
            {featuredMovies.map((movie, index) => (
              <MovieCard key={index} {...movie} />
            ))}
          </div>
        </div>
      </section>

      {/* QR Code Section */}
      <section className="py-16 bg-card/5">
        <div className="container mx-auto px-4">
          <div className="max-w-md mx-auto">
            <QRCodeGenerator />
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t border-border/30 py-8 bg-card/10">
        <div className="container mx-auto px-4 text-center">
          <p className="text-muted-foreground">
            © 2024 FlickScan. Discover your next favorite movie.
          </p>
        </div>
      </footer>
    </div>
  );
};

export default Index;
