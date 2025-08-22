
import React, { useEffect, useMemo, useState } from "react";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { Github, Linkedin, Mail, Phone, ExternalLink, Award, Briefcase, Code, Sun, Moon, MapPin, Download } from "lucide-react";

// Data from Nidhi K M's Resume
const profile = {
  name: "Nidhi K M",
  title: "Software Developer | B.E in Information Science & Engineering",
  location: "Davangere, India",
  email: "nidhikm975@gmail.com",
  phone: "9632358124",
  summary:
    "Motivated and detail-oriented B.E. graduate in Information Science with strong technical foundation. Passionate about solving real-world challenges, teamwork, and continuous learning.",
  avatar:
    "https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=300&auto=format&fit=crop", // Replace with your photo
  social: {
    github: "https://github.com/", // Add GitHub link
    linkedin: "https://www.linkedin.com/", // Add LinkedIn link
    resume: "/resume.pdf", 
  },
};

const skills = {
  technical: ["Java", "C", "Python", "HTML", "CSS", "JavaScript", "MySQL", "PHP"],
  soft: ["Multitasking", "Leadership", "Fast Learner", "Teamwork", "Communication"],
  certifications: ["MongoDB", "Power BI for Beginners", "Web Development"]
};

const projects = [
  {
    title: "Tourism Management System",
    description:
      "Developed a responsive system using HTML, CSS, JS, MySQL, and PHP to manage tourism-related data and booking features.",
    tech: ["HTML", "CSS", "JavaScript", "MySQL", "PHP"],
    image:
      "https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop",
    links: {
      demo: "#",
      code: "#",
    },
  },
  {
    title: "Health Schemes Management System",
    description:
      "Built a secure system with user authentication, CRUD operations, and a categorized database to manage health scheme information.",
    tech: ["PHP", "MySQL", "HTML", "CSS", "JS"],
    image:
      "https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=1200&auto=format&fit=crop",
    links: {
      demo: "#",
      code: "#",
    },
  },
];

const achievements = [
  {
    title: "MongoDB Certification",
    org: "MongoDB University",
    blurb: "Gained proficiency in NoSQL database management and queries.",
  },
  {
    title: "Power BI for Beginners",
    org: "Certification Course",
    blurb: "Learned basics of Power BI dashboards and business intelligence reporting.",
  },
  {
    title: "Web Development Certificate",
    org: "Certification Course",
    blurb: "Completed training on full-stack web development technologies.",
  },
];

const experiences = [
  {
    role: "B.E Student",
    company: "Bapuji Institute of Engineering & Technology (BIET)",
    period: "2022 – Present",
    points: [
      "Studying Information Science and Engineering, expected graduation 2026.",
      "Engaged in academic projects, coding competitions, and certifications.",
    ],
  },
  {
    role: "Internships/Training",
    company: "Various Online Platforms",
    period: "2023 – 2024",
    points: [
      "Completed certifications in MongoDB, Power BI, and Web Development.",
      "Developed real-world project prototypes for practice.",
    ],
  },
];

function Section({ id, title, icon: Icon, children }) {
  return (
    <section id={id} className="scroll-mt-24" aria-label={title}>
      <div className="max-w-6xl mx-auto px-4 md:px-6">
        <div className="flex items-center gap-3 mb-6">
          <Icon className="h-6 w-6" aria-hidden />
          <h2 className="text-2xl md:text-3xl font-semibold">{title}</h2>
        </div>
        {children}
      </div>
    </section>
  );
}

export default function Portfolio() {
  const [dark, setDark] = useState(true);

  useEffect(() => {
    const root = document.documentElement;
    if (dark) root.classList.add("dark");
    else root.classList.remove("dark");
  }, [dark]);

  const nav = useMemo(
    () => [
      { href: "#about", label: "About" },
      { href: "#skills", label: "Skills" },
      { href: "#projects", label: "Projects" },
      { href: "#achievements", label: "Achievements" },
      { href: "#experience", label: "Experience" },
      { href: "#contact", label: "Contact" },
    ],
    []
  );

  return (
    <div className="min-h-screen bg-white text-zinc-900 dark:bg-zinc-950 dark:text-zinc-50 transition-colors">
      {/* Nav, Hero, About, Skills, Projects, Achievements, Experience, Contact, Footer remain same as starter template but use updated data above */}
    </div>
  );
}