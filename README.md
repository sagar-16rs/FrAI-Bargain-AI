# FrAI-Bargain-AI 🛒💬

> *Bringing the warmth of Indian bazaar haggling to modern e-commerce*

An AI-powered conversational negotiation system that enables natural language price bargaining on e-commerce platforms. Built for the **AWS AI for Bharat Hackathon**, this project bridges the gap between rigid online pricing and India's relationship-based buying culture.

## 🎯 Project Vision

Bargain-AI transforms e-commerce by introducing the "joy of a good deal" through AI-powered haggling. Instead of fixed prices, users can negotiate naturally in Hinglish with an AI shopkeeper that understands cultural nuances, builds rapport, and offers personalized deals while protecting seller margins.

## Key Features

### **Natural Conversation Interface**
- Real-time chat overlay on product pages
- Voice-first support with Hinglish recognition
- Cultural adaptation for different user segments (Tier-1/2/3)
- WhatsApp-style familiar interface

### **AI-Powered Negotiation**
- AWS Bedrock (Claude 3.5) for intelligent responses
- "Ramesh" persona - warm, respectful digital shopkeeper
- Strategic negotiation tactics (flinch, build-up, closing)
- Sentiment detection and adaptive responses

### **Smart Pricing Engine**
- Strict floor price protection with guardrail layer
- Dynamic bundle suggestions and cross-subsidization
- Cart-aware pricing for multi-item optimization
- Secure 15-minute checkout tokens

### **Gamification & Social Sharing**
- Bargain skill scoring (Bronze/Silver/Gold/Platinum)
- "Better than X% of buyers" achievements
- Shareable victory cards for social media
- Viral loop encouraging user engagement

### **Multi-language Support**
- Hindi, English, and Hinglish combinations
- Code-switching detection and response
- Regional cultural adaptation
- Voice processing with Amazon Polly/Transcribe

## Architecture

### Serverless AWS Stack
```
React Chat Overlay → API Gateway (WebSocket) → Lambda Functions → AWS Bedrock
                                    ↓
                              DynamoDB (Sessions/Analytics)
                                    ↓
                              Guardrail Layer (Price Protection)
```

### Core Components
- **Negotiator Service**: AI conversation processing
- **Guardrail Layer**: Deterministic price validation
- **Session Manager**: WebSocket connection handling
- **Voice Processor**: Speech-to-text/text-to-speech
- **Analytics Engine**: Real-time performance tracking

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and npm
- AWS CLI configured
- Python 3.11+ for Lambda functions
- AWS SAM CLI for local testing

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/sagar-16rs/FrAI-Bargain-AI.git
cd FrAI-Bargain-AI
```

2. **Install dependencies**
```bash
# Frontend dependencies
npm install

# Backend dependencies (Lambda functions)
cd src/lambda
pip install -r requirements.txt
```

3. **Configure AWS services**
```bash
# Deploy infrastructure
sam build
sam deploy --guided
```

4. **Set up environment variables**
```bash
cp .env.example .env
# Edit .env with your AWS credentials and endpoints
```

### Integration

Add to any e-commerce site with a simple script tag:

```html
<script src="https://cdn.bargain-ai.com/widget.js"></script>
<script>
  BargainAI.init({
    productId: 'prod-123',
    sellerId: 'seller-456',
    initialPrice: 999.99,
    containerId: 'bargain-widget'
  });
</script>
```

## Use Cases

### Scenario 1: The College Student
**Rahul** wants a ₹15,000 phone but only has ₹13,500
- **Input**: "Bhai, student hoon, thoda kam kar do"
- **AI Response**: Suggests bundle with accessories for ₹14,200
- **Outcome**: Win-win deal with protected margins

### Scenario 2: Inventory Clearance
**EthnicVibes** has 500 unsold kurtas from last season
- **Strategy**: AI negotiates privately vs. generic "50% OFF" banners
- **Result**: 30% faster clearance while maintaining brand perception

## Tech Stack

### Frontend
- **React** - Chat overlay component
- **TypeScript** - Type-safe development
- **WebSocket API** - Real-time communication
- **Tailwind CSS** - Responsive styling

### Backend
- **AWS Lambda** - Serverless compute
- **AWS Bedrock** - AI/ML services (Claude 3.5)
- **DynamoDB** - NoSQL database
- **API Gateway** - WebSocket & REST APIs
- **Amazon Polly/Transcribe** - Voice processing

### AI/ML
- **LangChain** - Conversation state management
- **Claude 3.5 Sonnet** - Natural language processing
- **Custom prompt engineering** - Cultural adaptation
- **Property-based testing** - Correctness validation

## Performance Metrics

### Target KPIs
- **8-12%** conversion uplift for price-sensitive visitors
- **25%** reduction in inventory days for slow-moving SKUs
- **15%** decrease in price-related cart abandonment
- **Sub-2 second** AI response times
- **99.9%** uptime during peak shopping periods

## Security & Compliance

### Price Protection
- Deterministic guardrail layer prevents AI hallucinations
- Server-side validation of all price calculations
- Audit logging for all pricing decisions
- Rate limiting and manipulation detection

### Data Privacy
- Session-based data with automatic cleanup
- No permanent storage of personal conversations
- GDPR-compliant data handling
- Secure token-based checkout system

## Testing Strategy

### Dual Approach
- **Unit Tests**: Specific scenarios and edge cases
- **Property-Based Tests**: Universal correctness properties

### Key Properties Tested
- Floor price invariant (never below minimum)
- Token lifecycle security (15-minute expiry)
- UI responsiveness (sub-2 second responses)
- Voice processing accuracy (85%+ for Hinglish)

## Analytics & Insights

### Seller Dashboard
- Real-time negotiation success rates
- Average discount percentages
- Conversion rate comparisons
- Revenue impact analysis
- Inventory velocity improvements

### User Engagement
- Bargain skill progression tracking
- Social sharing metrics
- Session duration and satisfaction
- Language preference analytics

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## AWS AI for Bharat Hackathon

This project was developed for the AWS AI for Bharat Hackathon, focusing on:
- **Cultural Relevance**: Understanding Indian buying behavior
- **Language Inclusion**: Supporting Hinglish and regional preferences  
- **Economic Impact**: Democratizing negotiation for Tier-2/3 users
- **Technology Innovation**: Serverless AI at scale

## Contact & Support

- **Team**: Sagar (sagar-16rs)
- **Email**: ryss11091986@gmail.com
- **Project**: [GitHub Repository](https://github.com/sagar-16rs/FrAI-Bargain-AI)

---

